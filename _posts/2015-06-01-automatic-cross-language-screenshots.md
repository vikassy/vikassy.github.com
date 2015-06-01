---
layout: post
title: "Automatic cross language screenshots"
description: "Making Translated Screenshots with no effort"
category: Mediawiki
tags: [Mediawiki, VisualEditor, Selenium, Ruby]
---
{% include JB/setup %}
Pre GSOC
========
I had applied for GSOC in 2013, but was not selected. In 2014 I decided to spend enough time preparing my proposal before official GSOC organizations were listed.  I was googling around for organizations which uses ruby(my favorite programming language) and one among them was Mediawiki. Mediawiki had a neat page explaining each of their project ideas and I quickly scrolled down to the project which uses ruby.
<br /><br />
  I read the idea by [Amir E Aharoni](http://wikimediafoundation.org/wiki/User:Aaharoni-WMF), twice/thrice and I mailed him for more information. It took me some time to figure out the problem statement. He introduced me to [Zeljko](http://wikimediafoundation.org/wiki/User:ZFilipin_(WMF))(God of Selemiun in Wikimedia), who helped me get my first patch merged. We also had [pair programming](http://www.mediawiki.org/wiki/Pair_programming_for_fun_and_profit) where I learnt how to use jenkins and cloudbees. I also came up with a small proof of concept for the idea, by hardcoding it to specific scenario.

### Problem Statement ###

MediaWiki is a large and complex piece of software, and the user guide for core and those for extensions (like VisualEditor) each have a large number of images illustrating functions and stages of operation. However, these often date quickly as the software changes, and are generally only available in English or at best a few languages, which means that non-English users are not as well served.

<br />

<figure>
    <img src="/assets/images/before_deploy.jpg" alt="Image of VisualEditor Before Language Screenshots" style="width: 700px;"/>
    <figcaption style="text-align: center;">Part of VisualEditor user guide(in Hebrew language) before Language Screenshot deployment</figcaption>
</figure>

<br />

### Mediawiki Selenium ###

[Mediawiki Selenium](https://github.com/wikimedia/mediawiki-selenium.git) is a ruby gem used for browser testing for various projects in Mediawiki including VisualEditor. One of the features of gem was capturing to take screenshot of browser, whenever a particular scenario/browser test fails. This feature lead to the idea of cross site language screenshot.

GSOC Period
===========
I and Amir decided to meet(Skype or Hangout) twice every week around 06:00 pm IST. I started out by writing some browser tests for VisualEditor. [Chris McMahon](http://www.mediawiki.org/wiki/User:Cmcmahon) helped me in understanding page object model. Then I continued with my proof of concept by making it more generalized, so that all the scenario can be covered. This lead to my first and most important [patch](https://gerrit.wikimedia.org/r/#/c/135616/) of the project. [Nik Everett](https://en.wikipedia.org/wiki/User:NEverett_(WMF)) reviewing my patch and helped me making it more efficient and rubyist.

### Cropping ###

One of the problems which I faced during the project was of cropping various elements(it can be a simple div/span) of a HTML page. Many scenarios had multiple elements(a div/span any html tag) to be cropped. We solved this by using [minimum bounding rectangle(MBR)](http://en.wikipedia.org/wiki/Minimum_bounding_rectangle). 

<figure>
    <img src="/assets/images/cropping_algo.png" alt="Image of VisualEditor Before Language Screenshots" style="width: 700px;"/>
    <figcaption style="text-align: center;">Using MBR to get the required image for UserGuide</figcaption>
</figure>

<br />

### TDD ###
Zeljko started to review my code and first thing we did was to separate the language screenshot scenarios from normal VisualEditor browser tests to avoid confusions. This was the time I realized that my code was not only taking screenshots, but also was testing various VisualEditor features.

One of the most amazing part of the GSOC was me failing to explain Zeljko on how my code works. All I could understand from this was my code was not good enough. Zeljko helped me to solve this by using TDD i.e. test driven development. We decided to use [Rspec](https://github.com/rspec/rspec) and started pair programming. We assumed our own rectangle co-ordinates and wrote many unit tests to check if minimum bounding rectangle was working correctly.

When everything was green in specs, we started out by writting our browser tests to check if screenshots are getting cropped as expected. It not just ran on English, but also in different language like hebrew, german and many more. We all were excited to see everything working. 

### Birth of [LanguageScreenshotBot](https://commons.wikimedia.org/wiki/User:LanguageScreenshotBot) ###

Now we had screenshots for multiple languages, but we needed to upload all of them to [Wikimedia Commons](https://commons.wikimedia.org/wiki/Main_Page). We can upload the images manually, but we need a way to do it via some API, so that we can automate the whole process end-to-end. We decided to use MediaWiki web service API, but I was not able to upload my image via Postman REST client and was not sure what was going wrong. Amir Aharoni pointed me to [ApiSandbox](http://www.mediawiki.org/wiki/Extension:ApiSandbox), which can be used [easily](http://www.mediawiki.org/wiki/Special:ApiSandbox). I was not able to upload the images via ApiSandbox, as it does not support uploading of file from system, but it gave me good enoguh idea on how I can make it run on Postman client. Then we jumped to [Mediawiki Ruby API](https://github.com/wikimedia/mediawiki-ruby-api) and [implemented](https://gerrit.wikimedia.org/r/#/c/137451/) upload method.

Now we needed a bot which can be triggered by a jenkins job to upload the screenshots of VisualEditor userguide. Hence we requested for [bot permission](https://commons.wikimedia.org/wiki/Commons:Bots/Requests/LanguageScreenshotBot). Thanks to [Whatamidoing](https://commons.wikimedia.org/wiki/User:Whatamidoing_(WMF)) for helping me out with the exact numbers of images to be uploaded. Thanks to [Eugene Zelenko](https://commons.wikimedia.org/wiki/User:EugeneZelenko) for approving our bot.

### Jenkins Job ###

Everything was almost done, except we wanted a new jenkins job where we can run our browser tests for any number of specific languages and deploy it to commons using LanguageScreenshotBot. For this we used (parameterized build plugin)[https://wiki.jenkins-ci.org/display/JENKINS/Parameterized+Build] which allows you to enter parameter before you build the job. Thanks to [Antnoie Musso](https://www.mediawiki.org/wiki/User:Hashar) for helping us setup this jenkins job. Thanks to [Kartik Mistry](http://wikimediafoundation.org/wiki/User:KMistry_(WMF)), who helped us in solving tofu related problems, due to missing fonts.

### Conclusion ###

Hence we successfully converted screenshots of VisualEditor userguide to around 40 languages. Even though there is any change in UI of VisualEditor, one can update the userguide just by clicking the build command in Jenkins job.

<figure>
    <img src="/assets/images/after_deploy.png" alt="Image of VisualEditor Before Language Screenshots" style="width: 700px;"/>
    <figcaption style="text-align: center;">Part of VisualEditor user guide(in Hebrew language) after Language Screenshot deployment</figcaption>
</figure>
<br /><br />
Go checkout the [VisualEditor userguide](http://www.mediawiki.org/wiki/Help:VisualEditor/User_guide). Thanks to [Maggie Dennis](http://wikimediafoundation.org/wiki/User:Mdennis), [Guillaume Paumier](http://wikimediafoundation.org/wiki/User:Guillom) and [James Forrester](http://wikimediafoundation.org/wiki/User:Jdforrester_(WMF)) for helping me out in screenshots. I had a great fun learning lots of things and talking to awesome people.

Post GSOC
=========

We(mainly Amire and Zeljko) created gems out of above project called [screenshot](https://github.com/amire80/screenshot) and [commons_upload](https://github.com/amire80/commons_upload) which helps us to create screenshot for different projects. Also I plan to build another tool above this where one can take screenshot without any effort to code. Checkout a small [demo of it](https://www.youtube.com/watch?v=w7RlwhKwq6w). You can also catch us in [Wikimania 2015](https://wikimania2015.wikimedia.org/wiki/Main_Page) where we will be [presenting](https://wikimania2015.wikimedia.org/wiki/Submissions/Making_Translated_Screenshots_With_No_Effort) this project.

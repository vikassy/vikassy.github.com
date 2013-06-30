---
layout: post
title: "My Experience in Ruby Conference India 2013"
description: "Ruby Conference India"
category: conference
tags: [ruby, conference]
---
{% include JB/setup %}

<style type="text/css">

ul.tabs
{
    padding: 6px 0;
    font-size: 0;
    margin:0;
    list-style-type: none;
    text-align: center; /*set to left, center, or right to align the tabs as desired*/
}
        
ul.tabs li
{
    display: inline;
    margin: 0;
    margin-right:2px; /*distance between tabs*/
}
        
ul.tabs li a
{
    font: normal 12px Verdana;
    text-decoration: none;
    position: relative;
    z-index: 1;
    padding: 6px 16px;
    border: 1px solid #CCC;
    border-bottom-color:#AAA;
    color: #000;
    background: #F0F0F0 url(tabbg.gif) repeat-x 0 0;
    border-radius: 2px 2px 0 0;
    outline:none;
}
        
ul.tabs li a:visited
{
    color: #000;
}
        
ul.tabs li a:hover
{
    border: 1px solid #AAA;
    background:#F0F0F0 url(tabbg.gif) 0 -36px repeat-x;
}
        
ul.tabs li.selected a
{
    /*selected tab style */
    padding: 9px 16px 6px;
    position: relative;
    top: 0px;
    font-weight:bold;
    background: white url(tabbg.gif) 0 -72px repeat-x;
    border: 1px solid #AAA;
    border-bottom-color: white;
}
        
        
ul.tabs li.selected a:hover
{
    /*selected tab style */
    text-decoration: none;
}
        
div.tabcontent
{
    display: block;
}

div.tabcontents
{
    border: 1px solid #AAA; padding: 30px;
    background-color:#FFF;
    border-radius: 2px;
}
</style>

<script type="text/javascript">
<!--//--><![CDATA[//><!--

var tabs=function(){var b=function(c,a){var b=new RegExp("(^| )"+a+"( |$)");return b.test(c.className)?true:false},j=function(a,c){if(!b(a,c))if(a.className=="")a.className=c;else a.className+=" "+c},h=function(a,b){var c=new RegExp("(^| )"+b+"( |$)");a.className=a.className.replace(c,"$1");a.className=a.className.replace(/ $/,"")},g=function(c,b){var a=document.getElementsByTagName("html");if(a)a[0].scrollTop+=b},e=function(){var b=window.location.pathname;if(b.indexOf("/")!=-1)b=b.split("/");var a=b[b.length-1]||"root";if(a.indexOf(".")!=-1)a=a.substring(0,a.indexOf("."));if(a>20)a=a.substring(a.length-19);return a},d=e(),c=function(a){this.a=0;this.b=[];this.c=[];this.d=[];this.e=0;this.f(a)};c.prototype={g:function(b){var c=new RegExp(d+b+"=(\\d+)"),a=document.cookie.match(c);return a?a[1]:this.h()},h:function(){for(var a=0,c=this.d.length;a<c;a++)if(b(this.d[a],"selected"))return a;return 0},j:function(d,c){for(var b=d.getAttribute("rel"),a=0;a<this.b.length;a++)if(this.b[a].getAttribute("rel")==b){j(this.b[a].parentNode,"selected");c&&this.e&&this.k(this.a,a)}else h(this.b[a].parentNode,"selected");this.l(b)},k:function(a,b){document.cookie=d+a+"="+b+"; path=/"},l:function(b){for(var a=0;a<this.c.length;a++)this.c[a].style.display=this.c[a].id==b?"block":"none"},m:function(a){if(a.id)for(var b=0;b<this.b.length;b++)if(this.b[b].getAttribute("rel")==a.id)return this.b[b];return a.parentNode.nodeName!="BODY"?this.m(a.parentNode):null},n:function(d,c){var a=document.getElementById(d);if(a){var b=this.m(a);if(b){this.j(b,0);if(!c)setTimeout(function(){a.scrollIntoView();g(a,-120)},0);else setTimeout(function(){window.scrollTo(0,0)},0);return 1}else return 0}},f:function(a){this.a=a.i;this.b=a.getElementsByTagName("a");this.d=a.getElementsByTagName("li");for(var b=0;b<this.b.length;b++)if(this.b[b].getAttribute("rel")){this.c.push(document.getElementById(this.b[b].getAttribute("rel")));var f=this;this.b[b].onclick=function(){f.j(this,1);return false}}var e=a.getAttribute("persist")||"";this.e=e.toLowerCase()=="true"?1:0;var d=window.location.hash;if(d&&d.length>1)if(this.n(d.substring(1),window.location.search.indexOf("noscroll=true")>-1))return;var c=this.e?parseInt(this.g(a.i)):this.h();if(c>=this.b.length)c=0;this.j(this.b[c],0)}};var a=[],i=function(d){var b=false;function a(){if(b)return;b=true;setTimeout(d,4)}if(document.addEventListener)document.addEventListener("DOMContentLoaded",a,false);else if(document.attachEvent){try{var e=window.frameElement!=null}catch(f){}if(document.documentElement.doScroll&&!e){function c(){if(b)return;try{document.documentElement.doScroll("left");a()}catch(d){setTimeout(c,10)}}c()}document.attachEvent("onreadystatechange",function(){document.readyState==="complete"&&a()})}if(window.addEventListener)window.addEventListener("load",a,false);else window.attachEvent&&window.attachEvent("onload",a)},f=function(){for(var e=document.getElementsByTagName("ul"),d=0,f=e.length;d<f;d++)if(b(e[d],"tabs")){e[d].i=a.length;a.push(new c(e[d]))}};i(f);return{open:function(c,d){for(var b=0;b<a.length;b++)a[b].n(c,d)}}}()


//--><!]]>
</script>

<a href="http://rubyconfindia.org/">
  <img src="http://rubyconfindia.org/2013/assets/images/badges/186.png" 
   alt="I am sponsoring RubyConf India 2013">
</a>
<ul class="tabs" persist="true">
    <li class="selected"><a href="#" rel="view1">Day1</a></li>
    <li class=""><a href="#" rel="view2" id="link2">Day2</a></li>
</ul>
<div class="tabcontents">
    <div style="display: block;" id="view1" class="tabcontent">
      <h3>Journey towards the conference</h3>
        I live in NITK Surathkal(which is 367 kms from Bangalore) during college days and in Bangalore during holidays.I started using ruby in first year of my college and discovered about BRUG(Bangalore Ruby User Group). I attended various talks and met lots of rubyist. There I met <a href="https://twitter.com/_prakash">Prakash Murthy</a> in May 2013. He told me about RubyConf India, where he was giving a talk on "Taking Ruby Community in India to a new level". Later I was selected for student scholarship program, with <a href="https://twitter.com/_prakash">Prakash</a> as my developer sherpa. 
        Here is my experince in RubyConf India 2013.<br /><br />
      <h3>Opening Keynote by Jim Weirich</h3>
        I sat in first row with <a href="https://twitter.com/_prakash">Prakash</a> and he introduced me to Jim. It was amazing experince to meet the man behind <a href="https://rubykoans.com">rubykoans</a>, which introduced me to test driven development. He told me that today we were gonna write some more test. In his talk I came to know about KataRomanCalculator. He started to write simple tests to check if RomanNumeralConverter could converts 1 to I. Then he passed it by returning "I". He similarly passed other test with n*"I"(where n is the given number). He then started to cover the case of 5 and it's multiple with simple if condition. He then continued this step covering all cases. I had never seen such a kind of development by writing tests. His work can be found in his <a href="https://github.com/jimweirich/presentation_kata_and_analysis">github</a>. <br /><br />
      <h3>Effective debugging by Jonathan Wallace</h3>
        I learnt basic debugging last semister in my college and was interested in this talk. He taught us debugging via a scenario using various debuggers. After his talk I asked him a doubt which I had in my mind for couple of months, i.e could I use these to debug large code repository like rails, as I wanted to understand rails internals. He told that it was possible. Later he suggested me to look at the various blogs and materials which would help me understand rails internals.<br /><br />
<!-- SPLIT -->
        <img src="/assets/images/jonathan.jpg" /> 
        Thank you Prakash for the pic. 
        <br /><br />
    <h3>Graph database and Pelting rubies</h3>
        After a stomach full, I came across new database which I had never heard of, i.e Graph Database. Nikhil also mentioned that graph design or structure, played an important role. I will soon be trying out <a href="http://www.neo4j.org/">neo4j</a> for one of my summer project. <br /><br />

        Again that evening I saw another surprising framework called metasploit. After being pariticipated in INCTF(See my last blog <a href="/automation/2013/06/06/how-we-automated-a-task-in-inctf/">post</a>), metaspoilt would help me in software testing and also other competitions. Ausmarton Fernandes exploited rails 2 server to get a command line. Everyone was shocked seeing such vulnerablitiy. I will try to write another blog post on this framework <br> <br>
    <h3>Evening talks</h3>

        I always thought github is a perfect web application, but it turned out that I was wrong. Siddhant showed us how difficult it was to navigate for them. Next time whenever I make any web application, I will take care that it will be easy for blind people also to navigate. 
        <br><br>

        Steve Klabnik, gave talk on Functional Reactive Programming. It was very new to me, but I learnt about streaming by using <a href="https://github.com/steveklabnik/frappuccino">frappuccino</a> gem
        <br><br>

        After such an amazing experience on the first day, I was looking forward for the next. 
        <a href="#" onclick="document.getElementById('link2').click()">Click here for day 2</a>
    </div>
    <div style="display: none;" id="view2" class="tabcontent">
    <h3>Ruby 5k</h3>
        I usually getup at 10 or 11 am, but this day it was 6!!! I thought 5km should be fun and easy, but it turned out to be a long one. I ran 2.5 km(or maybe less than that) and remaining was just a walk. <br><br>
        <img src="/assets/images/5k.jpg" width="100%" >
    <h3>Aaron Patterson and Ruby, Rock N Roll </h3>
        Today I realized that sitting in a conference is way more fun than watching it's video. Aaron patterson's talk was inspirational. I was happy to hear that he seriously started with ruby after using mechanize, which is similar in my case. I also got your Ruby sticker !! Thank you 
        <br><br>
        Sau Sheong Chang with his gem muse, created song with our tweets. He gave us an idea of music notes and beats which was tough to grasp for me. But it was fun and a great learning experience. 
        <br><br>
    <h3>Dissecting Ruby with Ruby</h3>
        I have been using heroku for 1 year and was pleased to see Richard Schneeman, who is working in heroku. Jonnathan had told to attend this as I would learn to debug programs using any debugger. Yes, it was done using ruby itself. I have started to use <a href="http://www.codetriage.com/">codetriage</a> and working hard to make some contributions in opensource. I bugged him a lot with all my doubt which I had on heroku, and got to know a lot of this in ruby. <br><br>
    <h3>Inside Git and Ruby in style</h3>
        Once I had given a <a href="Slideshare.net/VikasYaligar/git-presentation-15778897">talk</a> on git, but always wondered how it works. Shadab's gem <a href="https://github.com/shadabahmed/git_guts">git_guts</a> is a unique way of learning git internals. Using git on .git is a clever idea and the best way to understang git. I will soon write a blog post on git internals.
        <br><br>
        Bhavin's talk on writing ruby in style, showed how important it was to write good. I learnt how to write beautiful code. <br><br>
    <h3>Evening talks!!</h3>
        That evening Prakash took the Indian Ruby Community to whole new world. I sadly attended only half of his talk, as I was bugging Richard. But that half part was the ultimatum. I was luck to have him as developer sherpa in RubyConf India. I have decided to make one ruby group in NITK.
        <br><br>
        Nick Sutterer also known as apotonick, talked on OOP techniques in Rails. He showed us many gems which can been used to make our life easier in rails. I got to know about many gems like apotomo and cells. 
        <br><br>
        Andy Lindeman showed us that there were many open issues in github and we had to contribute to the opensource. Again this motivated me to do something for the opensource community. 
        <br><br>
    <h3>Conclusion</h3>
        This was my first conference and I learnt a lot. I would like to thank everyone in RubyConf India, for the brilliant event. I discovered how huge and helpfull the ruby community is. Thank you Prakash for guiding me. I had a great experience and looking forward for next RubyConf. 
    </div>
</div>
---
layout: post
title: "How we automated a task in InCTF"
description: "Automate the telent using expect."
category: automation
tags: [telnet, automation, hack, expect]
---
{% include JB/setup %}

###What is InCTF?

InCTF stands for Indian Capture the Flag, it's an naional level capture the flag contest in India conducted by Amritapuri, Kollam.
InCTF 2013 had 3 rounds, first round was learning round which taught us GRUB based hacking into linux and many more. Second round was toughest of all rounds and was amazing, here there was binary exploit, forensics, reverse engineering and web based exploits.
Final round was CTF game which goes for around 6 hours.

###Final round

In final round every team was given a Ubuntu server which can be run through virtual box. Each team had to hack root password of the server and start all the services(which was listed).
In InCTF 2013, there were 3 services i.e

<ul>
<li><b>Python server:</b> <br />
   This was a simple command line based server which allows one to create files and read files using commands like get and put. <br />
   Syntax: <br />
   <code>
   put file_name one_word_content</code> <br />
   <code>
   get filename
   </code></li>

<li><b>PHP based Apache server:</b> <br />
   This was a web server where one can signup and create his own private posts.
</li>
<li><b>C based Socket I/O server:</b> <br />
   This was again another command line based server where a user can signup and login to create a post. It had features like view users,posts.
</li>
</ul>
<!--break-->
### The problem

Our automation was on python based service, which allowed basic functionality of put and get on files. When we checked it's source in our server, we found out that all files related operations(create and read) were restricted to folder 'files/'.
We also found that 'files' folder had flags in 16 bits hash named files. If we could find the names of the files then flags could have been easily retrived from get command.
<p>
Not only that, it had a cpp file called worker which used to perform the actual task of read and write. The python script was only a medium for taking input from the user and check if it starts with get or put. If this is satisfied, then it would run the cpp executable with given input as command line arguments.
</p>
Also every 10 mins, old flag and files are changed by the game server.
### Our team's hack!

In final round of InCTF, I was a part of team ByteLandians with Dhruv, Abhay and Suresh.
<img src="/assets/images/bytelandians.jpg" alt="Drawing" style="width: 700px;margin-left: 0px"/>
We went through the source again, and found out that the worker program was checking for number of arguments based on command, where as python script was not doing that. This lead to a simple idea of running:
  <code> put file1 data;ls  </code>
Hurray it worked!! because, python would finally run the following command<code>./worker put file1 data;ls</code>. This means 'put' 'file1' and 'data' were arguments to ./worker, but ls was executed in command line.
The vulnerabilty was intense, as it allowed one to execute shell command. Hence we started to collect the flags by running <code>puts file1 data;cat files/*</code>
As there were 13 teams and every 10 mins new flags were added, writing script was a must.
<!--break-->
## The script

As we had to telnet the server, the pipeline based input through shell would not work. After searching we found out that we could use expect.
We installed expect using:
<pre>
<code>
sudo apt-get install expect</code></pre>

Then we wrote the following shell script(automate.sh):

    #!/usr/bin/expect

    spawn telnet 10.1.104.1 9090
    expect -re "> ?$"
    send "put file1 data;cat files/*"
    expect eof

Then we generalized it by changing spawn command to `spawn telnet $1 9090` and passed the ip address using the following python script(automate.py):

    import os
    ip = ["10.1.104.1","10.1.110.1"] #around 13 ip's in real game
    os.system("./automate.sh "+ip)

Then all we had to do was `python automate.py > flag_file`. Then we could submit the data inside the file every 10 mins.

###Result

This automation lead to collection of around 150 flags in 5 minutes. We were not able to collect much flag, as we ran our script very late. Also thanks to Dhruv, who was able to automate the web based service. With this we ended up being 3rd in the competition.


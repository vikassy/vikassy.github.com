---
layout: post
title: "My experience in NITK RUG 2013"
description: "NITK RUG Activities"
category: experience
tags: [NITK RUG,games,ruby,events]
---
{% include JB/setup %}


###What is NITK RUG?

NITK RUG is an unofficial group formed by ruby users in NITK. Currently we are 8 students who are part of various activities. For more information you can visit our <a href="http://nitkrug.herokuapp.com/">site</a>. 

###Activities

During the odd semester(July-November) of 2013, we were part of many activities. Some of them are listed below:

<ul>
<li><b>NITK RUG Website</b> <br />
  Thanks to Sriram and SKarthik for making an awesome <a href="http://nitkrug.herokuapp.com/">site</a> in 2 days. We were able to deploy it in heroku also. Aim of the site was to provide a brief idea of what the group does. 
</li><br />


<li><b>Dota2Alchemy</b><br />
  Dota, one of the famous multiplayer strategy game. Many students in our college play Dota and take part in many online competitions. One among them is Sushant, who decided to make a new website <a href="http://www.dota2alchemy.com/">www.dota2alchemy.com</a> so that people can auction unique Dota2 items. Sushant, SKarthik and Sriram made this site, which had about 15,000 unique visitors till now.
</li><br />

<li><b>Pacman game</b><br />
   As a part of NITK IEEE fest for first years, we worked on making a game(Pacman). To make it more fun we decided to make it realtime and multiplayer so that one team can compete with each other and the maximum the time spent by pacman wins. 
   <img src="/assets/images/pacman.jpg" alt="Pacman" style="width: 700px;margin-left: 0px"/>
   Some of the things we learnt while making this game are: 
  <ul>
    <li style="margin-left:15px;"><b>Move.js and Backbone</b></li>
    In front end we learnt to use move.js which we used to move the pacman in a map. Move.js is very easy to use and animation it provides is beautiful. Backbone is amazing, we just created a model called pacost [combination of Pacman and Ghost] and made its instances for pacmans and ghosts. When the user does keypress, javascript triggers a function of that ghost to change the direction and sends it to server about change in the direction. 
    <li style="margin-left:15px;"><b>Websockets</b></li>
    For making it real time we used websockets. We used the em-websocket gem in the backend. The function of backend was simple, i.e. to send messages to all the clients about changes in direction of a particular pacman/ghost. 
    <li style="margin-left:15px;"><b>Don't mess with real time systems</b></li>
    It is something I realized while testing the game. Initially we tested it with 3 player everything was working fine. But on the day of competition, we had a huge delay when we had 6 players. There was no satisfactory reason behind it and I was tensed about the event. Finally we changed some rules to make it just 1 pacman and 2 ghosts[that is the beauty of creating your own game], which had least delay.
    <li style="margin-left:15px;"><b>Mistakes</b></li>
    As this was the first time we were experimenting on realtime game, we made many mistakes. The biggest one was the delay, which made me conclude that I should never mess with realtime systems. But later we realized that the approach was not good, i.e to send the change in direction to the server because there was an assumption that all the pacman and ghost in each client are in same position. We could have solved it by sending the position and change in direction at the time of keypress by the user. 
    <li style="margin-left:15px;"><b>People</b></li>
    Thanks to all the NITK IEEE executive members who helped us to manage the game.Special thanks to Thejdeep,Sushant,SKarthik,Sriram who are the people behind the making of game. 
  </ul>  
</li>
<li><b>Airplanes Game</b><br/>
    Every odd semester we have a technical fest in NITK called Engineer. Many of us were in Comps committee. Inspired by WebGl used in our Engineer website, we decided to make another realtime multiplayer game based on WebGL. Finally we created a Aeroplane based game, where participants have to write an automated script to attack planes of opponents. This time the game was run in the Backend, except the shooting part. This time we used Babylon.js with em-websockets to make a 3D game. Babylon.js is awesome WebGL library, which is very easy to work out. This time we made equivalent backend i.e airplanes with positions. This time every millisecond the client sends the position to server and server sends it to everyone. This avoided the latency. Each success shoot was stored in a log file.After 20 mins we got a log file of 4GB, which we had to parse inorder to get the result.</li>
<li><b>Rails Rumble</b><br />
    We participated in Rails Rumble.Our idea was to make a website in which one can use the normal web tools to create a dynamic website and we would give him source of Rails when he is done with website. We were not able to complete it in right time, but we have resumed the work and planned to finish the beta version of by this December.</li>
<li><b>NITK IEEE project</b><br />
    As a part of NITK IEEE executive members, we can make projects. One of our project is to teach programming to students of schools and colleges in a software engineering way, i.e by creating a team and making a usable deployable product. First part of this is to teach students git. We are almost done with git part and final touch has to be given which we will be doing during this december.</li>
</ul>
### Future plan

We plan to finish all the pending projects next semester of our college.We are also planing to expand the group by holding various workshops in college. 
<!--break-->

---
layout: post
title: "Running npm start on Cloud9"
categories: Cloud9
tags: [documentation,sample]
image:
  feature: 
  teaser:  
  credit: 
  creditlink: ""
---
Recently I have just started on learning react. 
After experimenting on various text, I have decided to go with Cloud9.
Having multiple machines, Cloud9 being running on a cloud will make it much easier for me to continue my learning without breaking the flow. 

However, the first problem I faced was not able to run npm start as Cloud9 was being run on a virtual machine. 

After much googling, I found a way to fix it. 

First, you have to do npm install webpack-dev-server -g.

But I faced some issue installing. To solve this I have to update to a later version of npm.

To do that I ran, npm install npm@latest -g.

And finally to run your server webpack-dev-server  --host $IP --port $PORT  --hot --inline

Now everything seems to be running fine.

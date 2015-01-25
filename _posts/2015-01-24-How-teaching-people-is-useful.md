---
layout: post
title: 'How teaching people is useful'
---

I recently had expeditions at my school, a time where you spend 2 weeks doing an elective of your choice without regular classes. Of course the expedition I chose was computer science.

Since I know so much and this class is basic learning HTML, CSS, and JS I got to help the teacher (who is awesome) teach those things plus I got to work on projects at school.

Since all the students are using chromebooks it is hard to actually write the code but we have found a chrome app that allows you to edit files locally and save them but what we had to do was upload them to a server but the server we uploaded them to was using PHP for managing the files.

Since I personally think PHP is the worst programming language there is I decided to make my own file server like application with ruby. So, I locked myself in my room, and started writing down a basic way of organizing the application.

The basic way I came up was that I needed users so people only can modify their files and a directory to hold the files in.

So I looked up how to add users to sinatra and I found [warden](https://github.com/hassox/warden) for authentication, so I was then trying to find how to incorporate that into sinatra and then I found a simple tutorial that shows you how to add users and other things to a sinatra app.

Once I completed the users I started working on the permissions system. I sort of hacked it together using regex, mainly because since every person had a folder on the old server that was their first name then last name I decided to just use that model of naming. For the permissions system was create a simple regex matcher so the TA, me or the teacher could have access to all folders using the period wildcard operator in regex and for the rest of the users their regex would just match the folders name. If the regex equaled true I would allow them to upload and delete files from that directory.

Enough of the file listing app though.

The real reason of this post is to tell people how fun it can be to teach someone.

## Teaching, the joys

I really liked teaching people things even though sometimes it was just them asking a question or asking me to check their syntax and tell them what was wrong. But the I found the real joy when I actually helped people understand something from scratch.

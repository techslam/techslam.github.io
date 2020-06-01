---
title: "Change Jekyll Template - Easy Way"
date: 2019-10-11 21:30:00 +0800
categories: [Jekyll]
tags: [jekyll-template]
---

I am pretty new to using Jekyll for my blogging requirements. I have started to like the power of git to get the blogs update done. It's been a while I have created this blog , however I rarely updated anything here. 

When I set this blog up, I used the Jekyll theme called Pixyll, however , after couple of months I decided to update the look and feel of my blog and started browsing for some good themes and came across this 'Clean-Blog' theme. Problem was I wasn't sure how to update the theme in Jekyll. Found couple of articles online , but they are of no real help.

Since my blog was pretty new and just had one or two posts in it , I wasn't really worried playing around with it an taking the risk of messing it up. I finally managed to get the theme updated here. All I did was -

1. Downloaded the new theme zip file on my laptop and unzipped it.

2. Selected all the folder and files from this new theme and manually pasted it on my blog folder. Offcourse there were a number of conflicts for related files from both the themes.
I decided to discard all the old ones except for `_POST` folder and `_config.yml` file.

3. Ran below commands on my terminal -

```shell
git add --all

git commit -m "Change blog theme"

git push -u origin master
```

4. That's all, my blog is now live with new theme and it didn't break a thing. I did have to do some updates on the `_config.yml` file to match with the new theme requirements.

I still have to fix some issues with this new theme like 'get the contact form working etc...'

I understand this is not a cleanest and practical way of updating the theme, but like I said, my blog didn't have much stuffs that I was worried about getting corrupted with my experimentation. I still feel Jekyll community needs to come up with a good solution for updating the Jekyll theme without much hassles.

If you come across anything better, kindly drop me a line.
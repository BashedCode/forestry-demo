---
layout: post
title: Windows Perflib issues
sub_heading: ''
date: 2021-11-03 00:00:00 -0700
tags: []
banner_image: ''
related_posts: []

---
Tonight it seemed like my laptop was going to die. The CPU was maxed, even after stopping programs it seemed unresponsive. Finally, I was able to reboot and the same thing happened. This isn't normal for this system. It is snappy and quick most of the time with almost all the applications I throw at it.

I load the trusty Event Viewer to try to figure out what happening and notice errors I have seen many times before. A ".dll failed with error code The device is not ready. Performance data for this service will not be available." Keeps showing for a few different .dll files. I am sure I have seen this on other systems and never had to worry about it but I take the bait and look it up.

Getting to a Microsoft Answers page from earlier this year and I start reading. There is the usual MVP expert that wants users to try everything... Like everything to solve every issue. The last reply is shockingly a hit. Normally, it takes far longer to dig through the massive amount of data on the internet to find a solution.

Here it is (Source link Below):

A: Starting "Remote Registry" service in Task Manager "Services"

B: opening a CMD with administrator rights, and typing in:

    cd c:\windows\system32
    lodctr /R
    cd c:\windows\sysWOW64
    lodctr /R

Many thanks to AndersWWW for this answer.

[https://answers.microsoft.com/en-us/windows/forum/all/repeated-over-and-over-and-over-and-over-again/d951e7d6-b9ad-44d1-bfa3-49a94eae1fdc?LastReply=true#LastReply](https://answers.microsoft.com/en-us/windows/forum/all/repeated-over-and-over-and-over-and-over-again/d951e7d6-b9ad-44d1-bfa3-49a94eae1fdc?LastReply=true#LastReply "https://answers.microsoft.com/en-us/windows/forum/all/repeated-over-and-over-and-over-and-over-again/d951e7d6-b9ad-44d1-bfa3-49a94eae1fdc?LastReply=true#LastReply")
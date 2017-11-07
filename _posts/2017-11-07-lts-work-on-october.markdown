---
layout: post
title:  "My Debian LTS work on October"
date:   2017-11-07 07:30:14 -0300
categories: debian LTS contributions
---

In this post I describe the work that I've done until the end of October
in the context of the Debian LTS team. This month I was allocated 5h and spent
just 2h of them because I have written my master's qualification text (I am
almost on my deadline to finish it). During November I intend to finish these
3h pending, so I did not request more hours.

I basically worked with **CVE-2017-0903** which is an issue related to YAML
deserialization of gem specifications that could allow one execute remote code.
Two packages in wheezy could be affected by this security vulnerability,
**rubygems** and **ruby1.9.1**. The issue affects just RubyGems source code,
but before Ruby version 1.9.1 it was maintained in a separated package, after
that it was incorporated by ruby interpreter source package.

After carefully read the
[upstream blogpost](http://blog.rubygems.org/2017/10/09/unsafe-object-deserialization-vulnerability.html)
and reviewed the
[commit that intruduced this vulnerability](https://github.com/rubygems/rubygems/commit/3f2e05972c85d4f4d9cd5e56e5b033bfb4d11b84),
I was able to figure out whether the mentioned packages were affected or not.
The modification was not present in both of them, and after some tests I did
confirm that those versions of rubygems were not affected. The two packages
were marked as not affected by CVE-2017-0903 in wheezy.

Well, this was the summary of my activities in the Debian LTS team in
October.  See you next month :)

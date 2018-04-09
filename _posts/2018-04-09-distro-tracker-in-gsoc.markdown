---
layout: post
title:  "Migrating PET features to distro-tracker"
date:   2018-04-09 10:30:14 -0300
categories: debian PET distro-tracker
---

After joining the Debian Perl Team some time ago,
[PET](https://salsa.debian.org/kanashiro/pet3) has helped me a lot to find work
to do in the team context, and also helped the whole team in our workflow.  For
those who do not know what PET is: "a collection of scripts that gather
information about your (or your group's) packages. It allows you to see in a
bird's eye view the health of hundreds of packages, instantly realizing where
work is needed.". PET became an important project since about 20 Debian teams
were using it, including Perl and Ruby teams in which I am more active.

In Cape Town, during the DebConf16, I had a conversation with Raphael Hertzog
about the possibility to migrate PET features to distro-tracker. He is one of
the distro-tracker maintainers, and we found some similarities between those
tools. Altough, after that I did not have enough time to push it forward.
However, after the migration from [Alioth](https://alioth.debian.org/) to
[Salsa](https://salsa.debian.org/) PET became almost unuseful because a lot
of things were done based on Alioth. This brought me the motivation to get this
migration idea off the drawing board, and support the PET features in
[distro-tracker team's visualization](https://tracker.debian.org/teams/).

In the meantime, the Debian Outreach team published a
[GSoC](https://wiki.debian.org/SummerOfCode2018) call for mentors for this
year. I was a Debian GSoC student in 2014 and 2015, and this was a great
opportunity for me to join the community. With that in mind and the wish to
give this opportunity to others, I decided to become a mentor this year and
proposed a project to implement the PET features in distro-tracker, called
[Improving distro-tracker to better support Debian
Teams](https://wiki.debian.org/SummerOfCode2018/Projects/ImprovingDistro-trackerToBetterSupportDebianTeams).
We are at the selection students phase and I received great proposals. I am
looking forward to the start of the program and finally have the PET features
available in [tracker.debian.org](https://tracker.debian.org/). And of course,
bring new blood to the Debian Project, since this is the idea behind those
outreach programs.

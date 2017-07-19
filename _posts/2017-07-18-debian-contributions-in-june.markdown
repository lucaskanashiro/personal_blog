---
layout: post
title:  "My contributions to Debian in June"
date:   2017-07-18 22:15:14 -0300
categories: debian contributions
---

In this first post I intend to present my contributions to Debian Project
during the last month (June). I am kind of late, I am trying to make time to
create this blog since the beginning of the month, but my idea is to every
month make a post with all my contributions during the last month. This will
serve me as a log of my work.

During June, I worked on Debian Perl Group and Debian LTS teams stuff. After
the release of [Debian Stretch](https://www.debian.org/News/2017/20170617),
the Debian's freeze was over and we were allowed to upload packages again to
unstable. Many Perl modules have not been up-to-date, so we started to work on
them. As a curiosity, Debian Perl Group is the team into Debian that maintains
the largest number of packages, more than 3300 packages! It is a great amount
of work to be done, if you want to join us have a look into this
[page](https://wiki.debian.org/Teams/DebianPerlGroup/Welcome). Below is the
list of all Perl related packages that I did something:

* libchatbot-eliza-perl (uploaded to unstable)
* libclass-ehierarchy-perl (uploaded to unstable)
* libdata-dmp-perl (uploaded to unstable)
* liblingua-translit-perl (uploaded to unstable)
* liblist-someutils-perl (uploaded to unstable)
* liblocal-lib-perl (uploaded to unstable)
* libmath-planepath-perl (uploaded to unstable)
* libmoosex-types-structured-perl (uploaded to unstable)
* libparanoid-perl (uploaded to unstable)
* libparse-plainconfig-perl (uploaded to unstable)
* libperinci-sub-util-perl (uploaded to unstable)
* libpgobject-simple-perl (updated in git repo, not uploaded yet - uploader forgot to push branches)
* libpgobject-simple-role-perl (updated in git repo, but WAITS-FOR: libpgobject-simple-perl >= 3)
* libspreadsheet-read-perl (waiting for new dependencies, not uploaded yet to
  unstable)
  - libspreadsheet-parsexlsx-perl (ITP bug filled and uploaded, waiting in NEW)
    - libgraphics-colorutils-perl (ITP bug filled and uploaded, waiting in NEW)
    - libcryptx-perl (ITP bug filled and uploaded, waiting in NEW)
* libstring-trim-more-perl (uploaded to unstable)
* libsub-uplevel-perl (uploaded to unstable)
* libtap-simpleoutput-perl (uploaded to unstable)
* libtest-moose-more-perl (uploaded to unstable)
* libtest-tcp-perl (uploaded to unstable)
* libtime-progress-perl (uploaded to unstable)
* libtoml-parser-perl (uploaded to unstable)
* libverilog-perl (uploaded to unstable)
* libversion-perl (uploaded to unstable)
* libxml-compile-perl (uploaded to unstable)

Sometimes update a Perl module with new upstream release is not so
straightforward, because some of them add new dependencies and these
dependencies add others dependencies, and then seems that I am in a
near-endless cycle. But I usually have fun! =)

As I said before, I worked on some packages on behalf of Debian LTS. In resume,
Debian LTS team fixes some security vulnerabilities, most of them are reported
as [CVEs](https://cve.mitre.org/), in old Debian releases. Currently, Wheezy is
maintained by Long Term Support Team, more info
[here](https://wiki.debian.org/LTS). This is not an easy task because you need
to check if that package version is affected by this vulnerability (sometimes
it is not), apply the fix (generally released by upstream, but commonly
backport the patch is a nightmare), and test the package again to verify if the
vulnerability is fixed and if you did not add any regression. Some people
consider it as an unpleasent work, but for me is an opportunity to learn new
stuff, each package that I have worked on I learned a bunch of things. You will
deal with different programming languages and paradigmas, different software
natures and so forth. Below is the list of my contributions related with LTS:

* drupal7 (uploaded to wheezy-security and sent DLA)
* exim4 (uploaded to wheezy-security and sent DLA)
* kdepim (claimed to work on ti)
* libffi (uploaded to wheezy-security and sent DLA)

These are my contributions to Debian in June. I intend to continue this monthly
report consistently, I hope this will be usefull for someone, at least for me
:)

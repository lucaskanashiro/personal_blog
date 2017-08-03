---
layout: post
title:  "My contributions to Debian in July"
date:   2017-08-02 13:30:14 -0300
categories: debian contributions
---

Continuing my series of posts about my contributions to free software world,
recently just to Debian. This month I did not have the time that I use to
have to do my hobby, mostly because I am organizing/attending the
[Advanced School of Science on Smart Cities](http://interscity.org/advanced-school/).
Many Researchers and students, mainly PhD ones, of all around the globe are
here in Sao Paulo to share their knowledge and learn a bunch of stuff about
Smart Cities. Have a look in the web site if you are interested on it.

Despite this I worked on some Debian packages in the beginning of the month.
The Debian Security Team filled the bug
[#868572](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=%23868572)
against ruby-mixlib-archive, related to CVE-2017-1000026. Basically the gem was
vulnerable to a directory traversal attack that allows attackers to overwrite
arbitrary files by using ".." in tar archive entries. Hleb Valoshka backported
the upstream fix to the Debian stable (Stretch) version, so I sponsored his
work and did the upload to stable. I also fixed this issue in unstable version.

I worked as well on Debian Perl Group packages, most of them I have updated
them to the latest upstream release. We are trying to keep them all up-to-date,
but as I said in the last post It is a hard task for the human power that we
actually have. Below is the list of the packages:

* libxml-sax-writer-perl (uploaded)
* libverilog-perl (uploaded)
* cpanoutdated (uploaded)
* libcache-fastmmap-perl (uploaded)
* liblog-report-perl (uploaded)
* libxml-compile-perl (uploaded)
* libpgobject-simple-perl (uploaded)
* libpgobject-simple-role-perl (uploaded)
* libxml-compile-perl (WAITS-FOR: liblog-report-perl >= 1.2)
* liblog-report-perl (WAITS-FOR: liblog-report-optional-perl >= 1.03)
* liblog-report-optional-perl (uploaded)
* libstring-print-perl (uploaded)
* libcryptx-perl (commit JSON dependencies as recommended)

The packages that was waiting for some dependencies update are not waiting now,
all of them are satisfied, but I have not had enough time to work on them.

Moreover, I worked on Debian LTS fixes as I have done since some months ago. In
August I will start my work as paid contributor in Debian LTS Team powered by
[Freexian](https://www.freexian.com/en/services/debian-lts.html), then probably
I will start to write posts about my Debian LTS work separatelly. Below is the
list of packages that I fixed some CVE:

* kdepim (mark as not affected in wheezy)
* xorg-server (uploaded and DLA sent)
* lucene-solr (uploaded and DLA sent)
* krb5 (claimed)

The CVE-2017-9604 was assigned to kdepim package which does not ensure that
a plugin's sign/encrypt action occurs during use of the Send Later feature,
which allows remote attackers to obtain sensitive information by sniffing the
network. But after some tests I figured out that the kdepim version in Debian
Wheezy (4:4.4.11.1+l10n-3) is not affected by this issue. 

The xorg-server had assigned two vulnerabilites: CVE-2017-10971 and
CVE-2017-10972. Both of them is related to endianness conversion, in the former
an user authenticated to an X Session could crash or execute code in the
context of the X Server by exploiting a stack overflow in the endianness
conversion of X Events. In the latter, uninitialized data in endianness
conversion in the XEvent handling of the X.Org X Server allowed authenticated
malicious users to access potentially privileged data from the X server. They
have been fixed in version 2:1.12.4-6+deb7u7.

A path validation issue was found in lucene-solr, CVE-2017-3163. Its handler
supports an HTTP API (/replication?command=filecontent&file=<file_name>) which
is vulnerable to path traversal attack. Specifically, this API does not perform
any validation of the user specified file_name parameter. This can allow an
attacker to download any file readable to Solr server process even if it is not
related to the actual Solr index state. This issue has been fixed in version
3.6.0+dfsg-1+deb7u2.

In the end of the month I claimed krb5 package to fix the CVE-2017-11368. I
will talk about it in next month's post.

And that was all for the last month. This week I am heading to Montreal where
will be hosted the [DebConf17](https://debconf17.debconf.org/), the most
expected conference in the year, at least for me. I hope see some fellow Debian
contributors, having some fun and hacking!

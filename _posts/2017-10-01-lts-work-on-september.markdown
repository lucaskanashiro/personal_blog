---
layout: post
title:  "My Debian LTS work on September"
date:   2017-10-01 13:30:14 -0300
categories: debian LTS contributions
---

In this post I describe the work that I've done until the end of September
in the context of the Debian LTS team. This month I was allocated 5h and spent
all of them fixing packages.

* **irssi**: I claimed irssi and uploaded the package fixing the security
issues bellow to wheezy-security. I also have requested release team to fix
them in jessie as well, as desired by the irssi maintainer, you can track it
[here](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=874377).

	* **CVE-2017-10965**: When receiving messages with invalid time stamps,
	Irssi would try to dereference a NULL pointer. Found by Brian 'geeknik'
	Carpenter of Geeknik Labs.

	* **CVE-2017-10966**: While updating the internal nick list, Irssi may
	incorrectly use the GHashTable interface and free the nick while updating
	it. This will then result in use-after-free conditions on each access of
	the hash table. Found by Brian 'geeknik' Carpenter of Geeknik Labs.

These security issues are fixed in version 0.8.15-5+deb7u3 in wheezy-security
and will be fixed in version 0.8.17-1+deb8u5 in jessie, as soon as release team
has reviewed the patch, to be released at jessie's next release point.

* **BlueZ**: A CVE was published related to bluetooth and I claimed BlueZ to
fix it in wheezy-security.

	* **CVE-2017-1000250**: The SDP server in BlueZ is vulnerable to an
	information disclosure vulnerability which allows remote attackers to
	obtain sensitive information from the bluetoothd process memory. This
	vulnerability lies in the processing of SDP search attribute requests. 

Well, this was the summary of my activities in the Debian LTS team in
September.  See you next month :)

---
layout: post
title:  "My Debian LTS work on August"
date:   2017-09-01 13:30:14 -0300
categories: debian LTS contributions
---

In this post I describe the work that I've done until the end of August
in the context of the Debian LTS team. This month I was allocated 20.25h and
during this time I did some uploads, tested some packages provided by another
member of the Debian LTS team, and added some extra information about some
packages.

* **php5**: During this month I claimed php5 twice and did two uploads. In the
end of the month Raphael Hertzog notified me that I shouldn't do that because
php5 has many security updates during a month and we want to release updates a
bit less often. Now I am aware :) Basically I fixed these two CVEs:

	* **CVE-2017-11628**: A stack-based buffer overflow in the
	zend\_ini\_do\_op() function in Zend/zend\_ini\_parser.c could cause a
	denial of service or potentially allow executing code. NOTE: this is only
	relevant for PHP applications that accept untrusted input (instead of the
	system's php.ini file) for the parse\_ini\_string or parse\_ini\_file
	function, e.g., a web application for syntax validation of php.ini
	directives.

	* **CVE-2017-12933**: The finish\_nested\_data function in
	ext/standard/var\_unserializer.re in PHP is prone to a buffer over-read
	while unserializing untrusted data. Exploitation of this issue may have an
	unspecified impact on the integrity of PHP.

These security issues are fixed in versions 5.4.45-0+deb7u10 and
5.4.45-0+deb7u11 respectively. This was my first time handling security issues
in a package of such importance for many users, so I spent a lot of time
testing it. I tried it with many web applications such as drupal7 and
wordpress.


* **krb5**: I really like this work because I've learned a new thing everyday,
MIT Kerberos was one of them. Basically, it is a system for authenticating
users and services on a network. You should take a look if you are interested
in this kind of service ;) I fixed the following CVE in this package:

	* **CVE-2017-11368**: An authenticated attacker can cause a KDC assertion
	failure by sending invalid S4U2Self or S4U2Proxy requests.


* **augeas**: This is a configuration editing tool. It parses configuration
files in their native formats and transforms them into a tree. Another new
package for me, but it is not so useful in my daily work. The CVE bellow was
fixed by me:

	* **CVE-2017-7555**: Heap-based buffer overflow due to improper handling
	of escaped strings. Attacker could send crafted strings that would cause
	the application using augeas to copy paste the end of a buffer, leading to
	a crash or possible code execution.


* **tenshi**: This is a log monitoring program, designed to watch one or more
log files for lines matching user defined regular expressions and report on the
matches. Seems that upstream is not so active anymore because it does not have
a new release for some time (all the Debian suites have the same version of
this packages since wheezy). However, they released a fix for this security
issue:

	* **CVE-2017-11746**: Tenshi creates a tenshi.pid file after dropping
	privileges to a non-root account, which might allow local users to kill
	arbitrary processes by leveraging access to this non-root account for
	tenshi.pid modification before a root script executes a `kill 'cat
	/pathname/tenshi.pid'` command.


* **wordpress**: This is a well known and full feature web blogging tool used
world wide. I usually have a lot of fun with this package and this time was
not different. Upstream released a patch that fixes the security issue in the
latest version and I backported the patch to apply in the wheezy one. The
current system redirects requests using hooks which is not available in the
wheezy version, so I needed to go deep in the code to understand what was going
on. It was a nice hacking! I fixed this CVE:

	* **CVE-2017-9066**: There is insufficient redirect validation in the HTTP
	class, leading to SSRF.


* **connman**: The Linux Connection Manager project provides a daemon for
managing Internet connections within embedded devices running the Linux
operating system. I did not have plenty of time to play with this package, but
I provided a fix to the following CVE:

	* **CVE-2017-12865**: Stack-based buffer overflow in "dnsproxy.c" allows
	remote attackers to cause a denial of service (crash) or execute arbitrary
	code via a crafted response query string passed to the "name" variable.


These were my uploads during August related to Debian LTS. Moreover, I tried
to help with other kind of tasks:

* **git-annex**: I claimed this package but I realized that I could not apply
the upstream patch that actually fixes the CVE-2017-12976 in the wheezy
package.  I am not a Haskell expert but this patch changes several SSH modules
that do not exist in this old version. In the end, I was not capable to check
whether this package is affected by this CVE. I unclaimed the package and
provided some information about what I saw for future work.

* **irssi**: The irssi's maintainers were notified almost three months ago
about some security issues in wheezy, and one of them said that they are not
very important and would do the upload with the fixes. So, I pinged them again
because I did not see any news about that. In short, I will prepare an upload
with the required fixes for jessie and wheezy versions. This will be part of my
work in September.

* **thunderbird**: Guido Günther provided some Debian packages that are fixing
some security issues in thunderbird and asked for some testing. I installed
them and got a try, did some basic tests, for example: configure an account,
create folder to filter emails, receive and send emails, create tasks and use
the calendar. As I am not an advanced thunderbird user, I could not do more
advanced stuff :) I sent a report to him.

Well, this was the summary of my activities in the Debian LTS team in August.
See you next month :)

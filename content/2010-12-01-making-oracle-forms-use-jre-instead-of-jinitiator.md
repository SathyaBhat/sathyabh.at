---
title: Making Oracle Forms Use JRE instead of Jinitiator
author: sathya
type: post
date: 2010-11-30T20:50:47+00:00
url: /2010/12/01/making-oracle-forms-use-jre-instead-of-jinitiator/




categories:
  - 'Oracle & PL/SQL Stuff'
tags:
  - Application Server
  - Forms
  - oracle
  - Oracle Forms
  - PL/SQL
  - work

---
By default, Oracle Forms Application Server serves Oracle Forms applications using the built-in [Jinitiator JVM][1]. While JVM works _swell_ with cutting edge browsers<sup><a href="#footnote_0_424" id="identifier_0_424" class="footnote-link footnote-identifier-link" title="IE6">1</a></sup> it pretty much crashes most of the other browsers<sup><a href="#footnote_1_424" id="identifier_1_424" class="footnote-link footnote-identifier-link" title="Firefox, IE7+">2</a></sup> and doesn't work at all in Chrome. There <a href="https://sathyabh.at/2009/06/27/fixing-internet-explorer-crash-on-launching-oracle-forms-application-with-jinitiator/" target="_blank">are workarounds</a> but the workarounds do not play well while working with multiple tabs.

<!--more-->

Here's a simple way to make the Application Server serve Oracle Forms Applications using JRE rather than the Jinitiator. Please remember to take a backup of your existing files!

Locate your formsweb.cfg file. It should be in $oracle_home/forms/server directory. Add the below lines to the section corresponding to your config= setting.

<pre class="brush:bash">baseHTMLjinitiator=basejpi.htm
jpi_download_page=https://www.oracle.com/technetwork/java/javase/downloads/index-jdk5-jsp-142662.html
jpi_classid=clsid:8AD9C840-044E-11D1-B3E9-00805F499D93
jpi_codebase=https://java.sun.com/update/1.5.0/jinstall-1_5-windows-i586.cab
jpi_mimetype=application/x-java-applet;version=1.4.2</pre>

Here's a brief explanation of each of these terms:

  * jpi_classid – The ClassID of the Sun JVM to use (Internet Explorer specific). Should be set to clsid:8AD9C840-044E-11D1-B3E9-00805F499D93 for dynamic versioning or to clsid:CAFEEFAC-<major version>-<minor version>-<patch version>-ABCDEFFEDCBA for static versioning
  * jpi_codebase – Download location of the CAB file for the Sun JVM (IE specific)
  * jpi\_mimetype – JPI\_MIMETYPE is a mime-type in a format like “application/x-java-applet;<version\_type>=<implementation\_version>”. For static versioning, <version_type> should be set to “jpi-version”. For dynamic versioning, this should be set to “version”.
  * jpi\_download\_page – This is the URL where Netscape/Firefox users can download the JRE.

Refer [here][2] for a detailed explanation of each of these terms. That's about it. Reloading the application should result in the JRE kicking in, rather than Jinitiator. Also ensure any jar files that you have are digitally signed, else you will run into an warning about blocking unsigned jar files which might lead to a showstopper bug.

<ol class="footnotes">
  <li id="footnote_0_424" class="footnote">
    IE6 [<a href="#identifier_0_424" class="footnote-link footnote-back-link">&#8617;</a>]
  </li>
  <li id="footnote_1_424" class="footnote">
    Firefox, IE7+ [<a href="#identifier_1_424" class="footnote-link footnote-back-link">&#8617;</a>]
  </li>
</ol>

 [1]: https://en.wikipedia.org/wiki/Jinitiator
 [2]: https://www.oratransplant.nl/2005/05/24/settings-for-dynamic-versioning-with-sun-jpi-and-oracle-forms/

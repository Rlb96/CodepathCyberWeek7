# Project 7 - WordPress Pentesting

Time spent: 7 hours spent in total

> Objective: Find, analyze, recreate, and document **a minimum of 3 (max of 5) vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1\. [x]  (Required) WordPress 3.6.0-4.7.2 - Authenticated Cross-Site Scripting (XSS) via Media File Metadata
- [x] Summary: 
- Vulnerability types: XSS Injection
- Tested in version: 4.1.1
- Fixed in version: 4.2.13
- [x] GIF Walkthrough:<a href="https://imgur.com/XAQ1OTz"><img src="https://i.imgur.com/XAQ1OTz.gif" title="source: imgur.com" /></a>
- [x] Steps to recreate: 
    - Add three or more media files to your wordpress library, insert "Let it go <noscript/><script>alert(document.cookie);</script>" into the description of the media file.
    - Create a new post and add the media file to the post as an audio playlist.
    - You should recieve an error message when you try to create the playlist.
- [x] Affected source code:
- [Link 2](https://github.com/WordPress/WordPress/commit/28f838ca3ee205b6f39cd2bf23eb4e5f52796bd7)


2\. [x]  (Required) WordPress <= 4.2 - Unauthenticated Stored Cross-Site Scripting (XSS)
- [x] Summary: 
- Vulnerability types: XSS
- Tested in version: 4.2
- Fixed in version: 4.2
- [x] GIF Walkthrough:<a href="https://imgur.com/Ba2rmj2"><img src="https://i.imgur.com/Ba2rmj2.gif" title="source: imgur.com" /></a>
- [x] Steps to recreate: Go to the comments section of the page. 
	 1) Log in as Admin
	 2) Enter in <script>while(1){alert(document.cookie);}</script> in the comments box.  
	  			Warning once you click submit, the page will refresh and you will have an infinite amount 
	 			of alert messages.
	3) to end the message, go to the info page and delete the comment.
- [x] Affected source code:
- [Link 1](https://compsecurityconcepts.wordpress.com/tag/cross-site-scripting/)

3\. [x] XSS Vulnerability in Twenty Fifteeen Theme (CVE 2015-3429)
- [x]  Summary:
			Vulnerability types: XSS
			Tested in version: 4.1
			Fixed in version: 4.2.2
			- By injecting a malicious script into 
			http://wp-url/wp-content/themes/twentyfifteen/genericons/example.html# an 
			attacker can hijack a privileged user's session, change the password, 
			and gain control of the system.
- [x] GIF Walkthrough:<a href="https://imgur.com/zIcJny1"><img src="https://i.imgur.com/zIcJny1.gif" title="source: imgur.com" /></a>
- [x] Steps to recreate:
			Navigate to http://wpdistillery.dev/wp-content/themes/twentyfifteen/genericons/example.html#
			Append a malicious image tag to the url: http://wpdistillery.dev/wp-content/themes/twentyfifteen/genericons/example.html#<img src=1 onerror=alert(1)>
			An alert dialog will appear. We have successfully executed an xss attack
- [x]  Affected source code:
			https://github.com/Automattic/Genericons/commit/798ac98579dd72dfdb11bdee3e7bebf01cffb1f7

## Assets
3 audio files made using quicktime audio recorder
- GIF created with [LiceCap](http://www.cockos.com/licecap/).

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes
Challenging but more fun as I started to get the hang of it

## License

Copyright [2017] [Ryan Butterfield]

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

# codepath_week7_8
Private repo for submitting week 7 and 8 assignment. 

# Project 7 - WordPress Pentesting

Time spent: **X** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) Authenticated Stored Cross-Site Scripting (XSS) - CVE-2015-5622
  - [X] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.3
  - [X] GIF Walkthrough:
      <img src="vulnerability_one/setupOne.gif"/>
      <img src="vulnerability_one/setupTwo.gif"/>
      <img src="vulnerability_one/setupThree.gif"/>
  - [X] Steps to recreate: 
      1. Create a user that create posts (Author or Contributor)
      2. Login to that user and create a post
      3. Using the HTML input mode, insert html with a HTML DOM Event inside ink tags. 
          Example: `<a href="[caption code=">]</a><a title=" onmouseover=alert('XSS!')  ">link</a>`
      4. Log out of the user and login as an administrator.
      5. View the page and hover over the link.
  - [X] Affected source code:
    - [Source File](https://core.trac.wordpress.org/changeset/33359)
2. (Required) Local URIs Server Side Request Forgery (SSRF) - CVE-2016-2222
  - [X] Summary: 
    - Vulnerability types: SSRF
    - Tested in version: 4.2
    - Fixed in version: 4.2.7
  - [X] GIF Walkthrough:
      <img src="vulnerability_two/setupOne.gif"/>
      <img src="vulnerability_two/setupTwo.gif"/>
  - [X] Steps to recreate: 
      1. Log into WordPress
      2. Create and host a webpage with malicious content similar to `<img src="//wpdistillery/wp-admin/press-this.php?u=http://0.0.0.0:8080&url-scan-submit=Scan" />`
      3. Visit the site while logged in to WordPress
  - [X] Affected source code:
    - [Source Code](https://core.trac.wordpress.org/changeset/36442)
3. (Required) Unauthenticated Stored Cross-Site Scripting (XSS) - CVE 2015-3440
  - [X] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.1
  - [X] GIF Walkthrough: 
      <img src="vulnerability_three/setupOne.gif"/>
  - [X] Steps to recreate: 
      1. Make a comment similar to `<a title='x onmouseover=alert(unescape(/XSS/.source)) style=position:absolute;left:0;top:0;width:5000px;height:5000px  AAAAAAAAAAAA...[64 kb]..AAA'></a>` except with 64,000 A's.
  - [X] Affected source code:
    - [Source Code](https://core.trac.wordpress.org/changeset/32299)
4. (Optional) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
5. (Optional) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php) 

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)
- [Info about CVE 2015-2213](https://blog.checkpoint.com/2015/08/11/finding-vulnerabilities-in-core-wordpress-a-bug-hunters-trilogy-part-ii-supremacy/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [2019] [Lee Ward]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.

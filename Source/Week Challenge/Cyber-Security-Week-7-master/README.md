# Cybersecurity Week 7 - *Zilone* 

Time spent: **8.5** hours spent in total 

## User Stories

The following **required** problems are completed:

1. [x]  Required: Exploit 1: XSS
2. [x]  Required: Exploit 2: User Enumeration
3. [x]  Required: Exploit 3: XSS2

The following advanced user stories are optional:

* [ ]  Bonus 1: Additional Exploit
* [ ]  Bonus 2: Additional Exploit 2

## Video Walkthrough

Here's a walkthrough of implemented user stories:

XSS, CVE-2016-7168, Test Version: WordPress 4.5.3, patched WordPress 4.6.1: 

The following is a vulnerability that allows users with editor or author privileges to run XSS on a WordPress site, running versions prior to 4.2.3. All that is required, is any user with the above privileges, who may proceed to embed cross site scripting on their post. This may be used for privilege escalation if users of admin privileges were to view the pages.

<img src='WordPress XSS.gif' title='WordPress XSS' width='' alt='' />

User Enumeration, WordPress 4.2:

The following is a vulnerability that allows anyone the ability to enumerate a list of valid user names on a WordPress site. Although more a design flaw than that of a technical flaw in code, this creates an easier brute force attack for any malicious hacker.

<img src='WordPress Username Enumeration.gif' title='WordPress Username Enumeration' width='' alt='' />

XSS 2, CVE-2017-9061, Test Version: WordPress 4.7.4, patched WordPress 4.7.5:

If a wordpress admin is tricked into attempting to load a bogus media file exceeding maximum allowed file size through upload.php, a carefully crafted file name will allow the execution of cross site scripting. This is due to the lack of file name sanitation. 

<img src='WordPress XSS2.gif' title='WordPress XSS2' width='' alt='' />

GIF created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

1. Vendor vulnerability disclosures are intentionally vague, which increases the difficulty of reproducing exploits on potential victims who may not have patched their software. 

## License

    Copyright [2017] [Michael Cheng]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.

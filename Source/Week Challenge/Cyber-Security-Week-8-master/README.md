# Cybersecurity Week 8 - *Zilone* 

Time spent: **30** hours spent in total 

## User Stories

## Lab

The following **required** problems are completed:

1. [x]  Required: Milestone 0: Preparing the Playing Field
2. [x]  Required: Milestone 1: Opening an Attack Surface
3. [x]  Required: Milestone 2: Recon
4. [x]  Required: Milestone 3: Hello, Metasploit
5. [x]  Required: Milestone 4: Pwnage
6. [x]  Required: Milestone 5: Tag it
7. [x]  Required: Milestone 6: Going Deeper
8. [x]  Required: Milestone 7: Hello, sqlmap


The following advanced user stories are optional:

* [ ]  Bonus 1: Bonus Milestone 8: sqlmap vs. SecurityShepherd (Optional)
* [ ]  Bonus 2: Bonus Milestone 9: Watch and Learn (Optional)

## Lab Video Walkthrough

Here's a walkthrough of implemented user stories:

Milestone 1: Opening an Attack Surface
<img src='Milestone 1.gif' title='Milestone 1' width='' alt='' />

Milestone 2: Recon
<img src='Milestone 2.gif' title='Recon' width='' alt='' />

Milestone 3: Hello, Metasploit
<img src='Milestone 3.gif' title='Recon' width='' alt='' />

Milestone 4: Pwnage
<img src='Milestone 4.gif' title='Recon' width='' alt='' />

Milestone 5: Tag it
<img src='Milestone 5.gif' title='Recon' width='' alt='' />

Milestone 6: Going Deeper
<img src='Milestone 6.gif' title='Recon' width='' alt='' />

Milestone 7: Hello, sqlmap
<img src='Milestone 7.gif' title='Recon' width='' alt='' />

## Assignment

The following **required** problems are completed:

1. [x]  Required: Challenge 1: Username Enumeration
2. [x]  Required: Challenge 2: Insecure Direct Object Reference
3. [x]  Required: Challenge 3: SQL Injection
4. [x]  Required: Challenge 4: Cross-Site Scripting
5. [x]  Required: Challenge 5: Cross-Site Request Forgery
6. [x]  Required: Challenge 6: Session Hijacking/Fixation

The following advanced user stories are optional:

* [ ]  Bonus 1: Bonus Objective 1: Build on Objective #3
* [ ]  Bonus 2: Bonus Objective 2: Build on Objective #4
* [ ]  Bonus 3: Advanced Objective: Build on Objective #4 and #6

## Assignment Video Walkthrough

Here's a walkthrough of implemented user stories:

Challenge Goal 1: Username Enumeration - Green Vulnerable
<img src='Challenge Goal 1 - Username Enumeration Green.gif' title='Challenge Goal 1' width='' alt='' />

Challenge Goal 2: Insecure Direct Object Reference - Red Vulnerable
<img src='Challenge Goal 2 - Insecure Direct Object Reference Red.gif' title='Challenge Goal 1' width='' alt='' />

Challenge Goal 3: SQL Injection - Blue Vulnerable
<img src='Challenge Goal 3 - SQL injection Blue.gif' title='Challenge Goal 1' width='' alt='' />

Challenge Goal 4: Cross-Site Scripting - Green Vulnerable
<img src='Challenge Goal 4 - Cross-Site Scripting Green.gif' title='Challenge Goal 1' width='' alt='' />

Challenge Goal 5: Cross-Site Request Forgery - Red Vulnerable
<img src='Challenge Goal 5 - Cross-Site Request Forgery.gif' title='Challenge Goal 1' width='' alt='' />

Challenge Goal 6:Session Hijacking/Fixation - Blue Vulnerable
<img src='Challenge Goal 6 - Session Hijacking Blue.gif' title='Challenge Goal 1' width='' alt='' />



GIF created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

1. Resolved a problem with Milestone 4 which prevented Windows users, with VirtualBox being unable to continue. Problem required set up with DHCP on virtual box in order to rectify. Troubleshooting the network problem resulted in the bulk of the time spent on this assignment.


## Concept Review
**Which attacks were easiest to execute? Which were the most difficult?**  
It’s hard to correctly state which attack is the easiest to perform. Finding the vulnerabilities is comparatively easy for Username Enumeration if you can create or know a valid user name. Similarly, Checking for SQL Injection vulnerabilities is as easy as placing a ‘ in the URL where input has something along the lines of ?userid=1. Although no actual attack + damage had occurred, the vulnerability became apparent. 

**What is a good rule of thumb which would prevent accidentally username enumeration vulnerabilities like the one created here?**  
A good rule of thumb to prevent username enumeration, is to just check the username and password combination. A simple AND statement comparing the validity of both, if the result is FALSE, simply load the same page stating so. In ways, a lazy developer provides a significantly smaller attack surface in this way.

**Since you should be somewhat familiar with the CMS and how it was coded, can you think of another resource which could be made vulnerable to an Insecure Direct Object Reference? What code could be removed which would expose it? (Hint: It was also the answer to the first bonus objective to the Weekly Assignment for week 3.)**  


**Many SQL Injections use OR as part of the injected code. (For example: ' OR 1=1 --'.) Could AND work just as well in place of OR? (For example: ' AND 1=1 --'.) Why or why not?**  
Although AND can still be used in some instances, OR followed by a true statement (such as 1=1) blanket converts any SQL query to TRUE, this bypasses certain checks (Such as login validations that are not sufficiently sanitized).

**A stored XSS attack requires patience because it could be stored for months before being triggered. Because of this, what important ingredient would an attacker most likely include in a stored XSS attack script?**  
One important ingredient that an attacker would most likely include in a stored XSS attack script is some form of notification which triggers and informs the attacker that the attack had been triggered. 

**Imagine that one of your classmates is an authorized admin for the site's CMS and you are not. How would you get them to visit the self-submitting, hidden form page you created in Objective #5 (CSRF)?**  
I could craft a webpage as a sample, for a possible update on the design for the site, and hide page as a hidden popup. When the friend visits the site, the invisible popup would load the information, and the backstabbed friend would have the page defaced.

**Compare session hijacking and session fixation. Which attack do you think is easier for an attacker to execute? Why? One of them is much easier to defend against than the other. Which one and why?**  
Session fixation is easier to pull off if a website allows session ID to be in the URL. Fixation is likely easier to defend against, by using Regenerating session identifiers. As a result, when authenticated, authorization will be stored on a new session ID.  

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

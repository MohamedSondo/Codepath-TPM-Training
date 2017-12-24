# Cybersecurity Pre-Work - *Zilone* 

Time spent: **6** hours spent in total 

## User Stories

The following **required** functionality is completed:

1. [x]  Required: Setup 
    -  [x]  Download and install Burp
    -  [x]  Configure your browser to direct traffic through Burp
    -  [x]  Can successfully view HTTPS traffic in sa
    -  [x]  Register an account at security.shephard.com
  
2. [x]  Required: Challenge 1 - HTTP Headers
3. [x]  Required: Challenge 2 - Basic Routes 1
4. [x]  Required: Challenge 3 - Query Params 1
5. [x]  Required: Challenge 4 - Insecure Direct Object References (IDOR)
6. [x]  Required: Challenge 5 - IDOR Challenge 1 

The following advanced user stories are optional:

* [x]  Bonus 1: IDOR Challenge 2 
* [x]  Bonus 2: IDOR Bank Challenge 3

## Video Walkthrough

Here's a walkthrough of implemented user stories:

HTTP Headers:  
<img src='http://i.imgur.com/6GWPJvm.gif' title='HTTP Headers' width='' alt='HTTP Headers' />

Basic Routes 1  
<img src='http://i.imgur.com/ZL0M3VG.gif' title='Basic Routes 1' width='' alt='Routes1' />

Query Params 1  
<img src='http://i.imgur.com/a6cT2Zu.gif' title='Query Params 1' width='' alt='Query' />

Insecure Direct Object References  
<img src='http://i.imgur.com/VAK7fvy.gif' title='Insecure Direct Object References' width='' alt='references' />

Insecure Direct Object Reference Challenge 1  
<img src='http://i.imgur.com/wZSOFHR.gif' title=' Direct Object Reference Challenge 1' width='' alt='challenge1' />

Insecure Direct Object Reference Challenge 2  
<img src='insecure direct object references challenge 2.gif' title='Direct Object Reference Challenge 2' width='' alt='challenge2' />

Insecure Direct Object Reference Bank  
<img src='Insecure Direct Object Reference Bank.gif' title='Direct Object Reference Bank' width='' alt='bonus' />

GIF created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Although the video walkthrough does not show it, it took a while to figure out that the hashed user ID was not any combination of name, nickname or other. The bulk of the time spent was in guessing the format. Eventually it dawned on me that the names were exactly the same as the previous problem, and the account numbers were likely hashes of the original.

Problems occured with the second bonus question. Could not get the correct input code after getting the funds. Logging off and logging back in, refreshing the page, and also logging out and back on code path did not seem to rectify the problem. 

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

# Cybersecurity Week 9 - *Zilone* 

Time spent: **5** hours spent in total 

## User Stories

## Lab

The following **required** problems are completed:

1. [x]  Required: Milestone 0: Networking Toolbox
2. [x]  Required: Milestone 1: Security-Flavored Net Tools
3. [x]  Required: Milestone 2: Grabbing Packets with tcpdump
4. [x]  Required: Milestone 3: Hello, Wireshark
5. [x]  Required: Milestone 4: Traffic Analysis - Mike's Computer is Acting Weird
6. [x]  Required: Milestone 5: Traffic Analysis - Mystery Meat Malware
7. [x]  Required: Milestone 6: Wi-Fi Hacking - Crack a Handshake
8. [x]  Required: Milestone 7: Wi-Fi Hacking - Grab a Handshake


The following advanced user stories are optional:

* [ ]  Bonus 1: Bonus Milestone 8: Wi-Fi Hacking - Sniff Thy Neighbor's Packets (Optional)


## Lab Video Walkthrough

Here's a walkthrough of implemented user stories:
Milestone 0: Writeup
<img src='Milestone 0 - Writeup.gif' title='Milstone 0' width='' alt='' />

Milestone 1: Security-Flavored Net Tools Challenge 1
<img src='Milestone 1 - Challenge 1.gif' title='Milestone 1' width='' alt='' />

Milestone 2: Grabbing Packets with tcpdump Challenge 1

http://i.imgur.com/kSPmkcs.gifv

Milestone 2: Grabbing Packets with tcpdump Challenge 2
<img src='Milestone 2 - Challenge 2.gif' title='Milestone2-2' width='' alt='' />

Milestone 3: Hello, Wireshark
<img src='Milestone 3 - Challenge 1.gif' title='Wireshark' width='' alt='' />

Milestone 4: Traffic Analysis - Mike's Computer is Acting Weird
<img src='Milestone 4.gif' title='Mike' width='' alt='' />

Milestone 5: Traffic Analysis - Mystery Meat Malware
<img src='Milestone 5.gif' title='Mystery' width='' alt='' />

Milestone 6: Wi-Fi Hacking - Crack a Handshake
<img src='Milestone 6.gif' title='Crack' width='' alt='' />

Milestone 7: Wi-Fi Hacking - Grab a Handshake
<img src='Milestone 7.gif' title='Grab' width='' alt='' />  
1. Handshake Packets are EAPOL protocol.  
2. Where is the SSID?  (Unsolved Question)
3. Where specifically is the hash? (Unsolved Question)  
4. A nonce is an arbitrary number that may only be used once. It is used in the hash functiosn for the protocol.  

## Assignment

The following **required** problems are completed:

1. [x]  Required: Installing and configuring an IDS or firewall
2. [x]  Required: Logging and analyzing network traffic
3. [x]  Required: Exposing specific vulnerabilities
4. [x]  Required: Honeypot, with basic writeup, must be reproducible.
5. [x]  Required: Demonstration: One proof-of-concept attack against honeypot that is detected/intercepted.

The following advanced user stories are optional:

* [ ]  Bonus 1: Bonus Objective 1
* [ ]  Bonus 2: Bonus Objective 2

## Basic Writeup:

1. Cloned MHN source and launched via Vagrant:  
Command Line>   
git clone https://github.com/threatstream/mhn.git  
cd mhn  
vagrant up  
/>   
The above creates the honeypot server, and the monitoring server  
  
2. Access shell on monitoring server:  
Command Line>  
vagrant ssh server  
/>  
  
3. Installed git within monitoring server:  
Command Line>  
sudo su -  
apt-get install -y git  
/>  

4. Apply patched fork due compatability issues:  
Command Line>   
cd /opt/  
git clone https://github.com/0x7fff9/mhn.git  
cd mhn  
git checkout 0x7fff9-encoding_patch  
/>  
  
5. Launch pre-requisite install scripts:  
Command Line from working directory: /opt/mhn/scripts>  
./install_hpfeeds.sh ; ./install_mnemosyne.sh ; ./install_honeymap.sh  
  
6. Fix "supervisorctl and hpfeeds-broker Fatal reading error:  
Command Line>  
./opt/hpfeeds/env/bin/python -m pip install --upgrade pyopenssl  
supervisorctl start hpfeeds-broker  
/>  
  
7. Modify mnemosyne config option to support private network deployment:  
Modify File: /op/mnemosyne/mnemosyne.cfg  
Change variable: ignore_rfc1918 to false  
  
8. Restart mnemosyne and run final server install script:  
Command Line>  
supervisorctl restart mnemosyne  
./install_mhnserver.sh  
/>  
  
9. Enter basic configuration:  
Do you wish to run in Debug mode?: y/n n  
Superuser email: YOUR-EMAIL@YOUR-SITE.com  
Superuser password:   
Superuser password: (again):     
Server base url ["http://1.2.3.5"]: http://10.254.254.100  
Honeymap url ["http://1.2.3.5:3000"]: http://10.254.254.100:3000  
Mail server address ["localhost"]:   
Mail server port [25]:   
Use TLS for email?: y/n y  
Use SSL for email?: y/n y  
Mail server username [""]:    
Mail server password [""]:   
Mail default sender [""]:   
Path for log file ["/var/log/mhn/mhn.log"]:   
  
10. Exit out of monitoring server:  
Command Line>  
exit  
exit  
/>  
  
11.Access admin console through browser: http://10.254.254.100  
  
12. Within Deploy page: Select Ubuntu - Dionaea as **Select Script**, copy Deploy Command  
  
13. Open Shell to Honeypot server through terminal:  
Command Line>  
vagrant ssh honeypot  
/>  
  
14. Open superuser shell and execute deploy command copied:  
Command Line>  
Sudo su -  
wget "http://10.254.254.100/api/script/?text=true&script_id=2" -O deploy.sh && sudo bash deploy.sh http://10.254.254.100 DuGSk2KT  
/>   
  
15. File to Patch values:  
Command Line>  
/etc/dionaea/dionaea.conf  
/usr/lib/dionaea/python/dionaea/ihandlers.  
/>  
  
16. Exit out of Honeypot server:  
Command Line>   
exit  
exit  
/>  
  
## Proof of Concept Video Walkthrough
<img src='Honeypot PoC.gif' title='PoC' width='' alt='' />



GIF created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

1.Proof of concept was done through the nmap method as described in the assignment. The attack initially registered, however, after shutting down both servers, and starting up again, nmap failed to record future attacks. 


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

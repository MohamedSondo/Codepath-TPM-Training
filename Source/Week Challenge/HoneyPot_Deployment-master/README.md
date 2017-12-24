# Project 9 - Honeypot

Time spent: **5** hours spent in total

> Objective: Setup a honeypot and provide a working demonstration of its features.

### Required: Overview & Setup

- [x] A basic writeup (250-500 words) on the `README.md` desribing the overall approach, resources/tools used, findings
	
	- I used docker to deploy a web application honeypot called Glastopf. I then exposed the server to the internet using ngrok and on another docker container used kali linux to attack it. Glastopf uses dork pages to emulate a vulnerable website. Glastopf can also emulate sqli vulnerabilities with either a MySQL or sqlite database as the back end database, however users also have the option to set up a Mongodb database as well. Furthermore, Glastopf can be set up to send email notifications when a certain attack pattern is detected or when any attack at all is detected. Lastly, Glastopf can log these attacks in order to be studied later. In order to test other honeypots which track malicious code and attacks against the server itself through methods such as ssh I also deployed MHN in an UBUNTU 14.04 instance using DigitalOcean. I couldn’t  deploy glastopf using MHN because there were port conflicts with other honeypots which i needed to deploy as well. 

- [x] A specific, reproducible honeypot setup, ideally automated. There are several possibilities for this:
	
	- To Install glastopf using docker in the terminal run:
		* $ mkdir -p /tmp/glastopf
		* $ cd /tmp/glastopf
		* $ wget https://raw.githubusercontent.com/glastopf/glastopf/master/Dockerfile
		* $ sudo docker build --rm --tag glastopf .
		* $ sudo mkdir -p /opt/honeypot/glastopf1
		* $ sudo docker run --rm --publish 80:80 --volume /opt/honeypot/glastopf1:/opt/myhoneypot glastopf
	
		* If there is an error when writing to the volume, I found that editing the permissions of the directory "/opt/honeypot/glastopf1" so that anyone can read and write will fix it.
	
	- To Install MHN using DigitalOcean:
		* create a droplet using either UBUNTU 12.04.5 or 14.04.5 
		* sudo apt-get update && sudo apt-get upgrade
		* sudo apt-get install git -y
		* cd /opt/
		* sudo git clone https://github.com/threatstream/mhn.git
		* cd mhn/
		* sudo ./install.sh
		* installation settings will come up for MHN, after installationg finishes run the following:
		* sudo /etc/init.d/nginx status
		* sudo /etc/init.d/supervisor status
		* sudo supervisorctl status
		* all processes should show running. and for the last one there should be 9 processes at least.
		* currently the install.sh is broken so if you get and error during installation, follow this link: https://github.com/threatstream/mhn/issues/441
		
		

### Required: Demonstration

- [x] A basic writeup of the attack (what offensive tools were used, what specifically was detected by the honeypot)
	
	* Against the glastopf honeypot I used sqlmap with kali lunux. The honey pot was able to detect the IP, program and payloads used against it as well as the paths being accessed by the program.
	
- [x] An example of the data captured by the honeypot (example: IDS logs including IP, request paths, alerts triggered)
 	
	* <a href="https://github.com/RedolentSun/HoneyPot_Deployment/blob/master/glastopf.log"/> Glastopf Logs </a>
	
- [x] A screen-cap of the attack being conducted
	* <img src='http://i.imgur.com/UgSej4u.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />
    
### Optional: Features
- Honeypot
	- [X] HTTPS enabled (self-signed SSL cert)
	- [ ] A web application with both authenticated and unauthenticated footprint
	- [X] Database back-end
	- [X] Custom exploits (example: intentionally added SQLI vulnerabilities)
	- [ ] Custom traps (example: modified version of known vulnerability to prevent full exploitation)
	- [ ] Custom IDS alert (example: email sent when footprinting detected)
	- [ ] Custom incident response (example: IDS alert triggers added firewall rule to block an IP)
- Demonstration
	- [X] Additional attack demos/writeups
	- [X] Captured malicious payload
	- [X] Enhanced logging of exploit post-exploit activity (example: attacker-initiated commands captured and logged)
	  
	* <img src='http://i.imgur.com/OCOExq5.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />

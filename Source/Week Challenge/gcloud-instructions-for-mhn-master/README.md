# How to set up gcloud vm 

## step 1
- click on cloud launcher from the drop down menu on the top left 
- <img src="https://i.imgur.com/QBJiNyF.png"></img>

## step 2
- scroll down to operating systems and choose Ubuntu Trusty linux 14.04 
- <img src="https://i.imgur.com/ABLCR1C.png"></img>

## step 3 
- click on launch compute engine 
- <img src="https://i.imgur.com/dbGb2CV.png"></img>

## step 4 
- on vm instances add a check to allow http traffic and create 
- <img src="https://i.imgur.com/4LJO7yy.png"></img>

## step 5 
- on next page that comes up click connect and choose open in browser window 
- <img src="https://i.imgur.com/PJ5ggyT.png"></img>

## step 6 
- run 
```bash 
sudo apt-get install -y git
cd /opt
sudo git clone https://github.com/RedolentSun/mhn.git
cd /mhn
sudo ./install.sh
```

## step 7

- after mhn finishes installation and you have set all mhn settings run the follwoing to make sure everything works:

```bash 
sudo /etc/init.d/nginx status
sudo /etc/init.d/supervisor status
sudo supervisorctl status
```

- the result of all of these should be running.

## step 8

- to allow traffic on certain ports edit the allow-http-traffic firewall rule by going to the menu
- scroll to vpc network and click firewall rules
- click default-allow-http 
- click edit and change protocols and port to Allow all
- click save and try attacking it now 

- <img src="https://i.imgur.com/sy9gPb8.png"></img>

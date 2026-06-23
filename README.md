AWS EC2 Nginx Automation Script

Overview
This project automates the installation and setup of an Nginx web server on an AWS EC2 instance using a Bash script.

Instead of manually installing and configuring Nginx, a single script handles the entire setup process.

 What This Project Does

- Updates system packages
- Installs Nginx web server
- Starts and enables Nginx service
- Automatically deploys a custom HTML webpage
- Confirms successful deployment


Technologies Used

- AWS EC2 (Ubuntu Linux)
- Nginx Web Server
- Bash Scripting
- Linux systemctl

How to Run
1. SSH into EC2 instance
ssh -i <your-key.pem> ubuntu@<EC2-PUBLIC-IP>
2. Create the script file
nano setup-nginx.sh
3. Paste the script and save
Paste the Bash script
Save file:
CTRL + X
Y
ENTER
4. Give execution permission
chmod +x setup-nginx.sh
5. Run the script
./setup-nginx.sh

Result

After running the script, the website will be accessible at:

http://<your-ec2-public-ip>

It will display:

My Automated Nginx Server

Script Overview

The automation script performs the following steps:

```bash
sudo apt update -y
sudo apt install nginx -y

echo "<h1>My Automated Nginx Server</h1>" | sudo tee /var/www/html/index.html

sudo systemctl enable nginx
sudo systemctl restart nginx





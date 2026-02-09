# AWS EC2 Nginx Web Server Deployment

## 📌Project Overview
Deployed a static website on AWS EC2 with a custom domain, with HTTPS using Let's Encrypt and integrates with Cloudflare for CDN.

## 🌐Live Deployment
Live Website: 
- https://gioulavloud.dev
- https://www.gioulacloud.dev

## Technologies
- AWS EC2
- Ubuntu Server
- Nginx Web Server
- UFW Firewall
- Linux System Administration

## ⚙️Deployment Process

### 1. AWS Infrastructure Setup
Created an EC2 instance using :
- Ubuntu Server 24.04 LTS
- Configures Security Groups to allow:
    - SSH (Port 22) -> restricted to my IP
    - HTTP (Port 80) -> 0.0.0.0/0
    - HTTPS (Port 443) -> 0.0.0.0/0
- Generated and secured SSH key pair

### 2. Server Access and Cinfiguration
- Connected to EC2 using SSH
- Updated system packages
- Installed and configured Nginx
- Enabled automatic service starup

Commands used:


``

sudo apt update && sudo apt upgrade -y


sudo apt install nginx -y


sudo systemctl enable nginx


sudo systemctl start nginx


sudo systemctl status nginx 

``

### 3. Website Deployment
- Created custom HTML webpage
- Verified accessibility locally and via public IP:

  
``
curl http://localhost
curl http://13.61.24.109
``

### 4. Security Hardening
- Configured UFW firewall
- Restricted unnecessary ports
- Created non-root administrative user

### 5. Configure Domain via Cloudflare
- Domain purchased gioulacloud.dev
- Cloudflare DNS configuration:

  
| Type  | Name   | Content        | Proxy     |
| :---- | :----: | :------------: | --------: |
| A     | @      | 13.61.24.109   | DNS Only  |
| A     | www    | 13.61.24.109   | DNS Only  |

- Initially i set proxy to DNS only to allow SSL insurance

### 6. Install HTTPS via Let's Encrypt
sudo apt install certbot python3-certbot-nginx -y
sudo certbot --nginx -d gioulacloud.dev -d www.gioulacloud.dev

- Added both domains to Nginx server block

``
server_name gioulavloud.dev www.gioulacloud.dev;
``

### 6. Re-enable Cloudflare Proxy
After verifying that HTTP & HTTPS work internally, i turned on orange cloud for CDN, caching and DDos protection




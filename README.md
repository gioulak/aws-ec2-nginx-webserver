# AWS EC2 Nginx Web Server Deployment

## 📌Project Overview
Deployed a cloud-hosted Linux web server using AWS EC2. The goal was to build a publicly accessible website while applying security, networking and system administration best practices.

## 🌐Live Deployment
Live Website: 
http://13.61.24.109/

## Technologies
- AWS EC2
- Ubuntu Server
- Nginx Web Server
- UFW Firewall
- Linux System Administration

## Architecture
User → Internet → AWS EC2 Instance → Nginx  Web Server → Static Website

## ⚙️Deployment Process

### 1. AWS Infrastructure Setup
- Created an EC2 instance using Ubuntu Server
- Configures Security Groups to allow:
    - SSH (Port 22)
    - HTTP (Port 80)
- Generated and secured SSH key pair

### 2, Server Access and Cinfiguration
- Connected to EC2 using SSH
- Updated system packages
- Installed and configured Nginx
- Enabled automatic service starup

Commands used:
sudo apt update && sudo apt upgrade -y
sudo apt install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx

### 3. Website Deployment
- Created custom HTML webpage
- Verified public accessibility via browser

### 4. Security Hardening
- Configured UFW firewall
- Restricted unnecessary ports
- Created non-root administrative user

## Skills Demonstrated 

Cloud Engineering:
- AWS EC2
- Security group configuration
- Cloud networking basics

Linux Administration:
- Package management
- Service cinfiguration
- User and permission management

## 🚀 Future Imprevements
- Implement HTTPS using SSL certificates
- Attach custom domain name
- Automate deployment using Terraform
- Deploy behind AWS Load Balancer
- Containerize application using Docker


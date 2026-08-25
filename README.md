# Networking Project - Domain + EC2 + DNS

## In this project , I will combining everything I have learnt which includes IP , DNS , Routing .

## The objective for this project is to Buy a domain, deploy NGINX on an EC2 instance, and make the page load over your own domain.

Steps :

 ## 1. Buy your own domain :
   - I am going to purchase the domain `abdinasiromar.org` on Cloudflare.
   -  Here it is :

    
   <img width="1339" height="538" alt="image" src="https://github.com/user-attachments/assets/98c0c8e8-fc7b-4455-b62a-286db5f7c1fa" />

 ## 2. Set up EC2 instance 
 - First click on Lauch instance on EC2 instance page :
    <img width="1599" height="181" alt="image" src="https://github.com/user-attachments/assets/208b1f25-c5b7-463c-994e-d8b52025fffa" />

 -  Then choose these following settings :
 -  AMI (Amazon Machine Image ) -  `Amazon Linux`
 -  Instance Type - `t3.micro` (Choose the free tier !)
 -  Add Key pair login (RSA)
 -  Security Groups :
     -  Allow SSH Traffic -> My IP address
     -  Allow HTTP -> port 80
     -  Allow HTTPS -> port 443


##  3. Connect to EC2 instance
-  We can connect to EC2 instance via SSH.
-  Use this command :
   ` ssh -i "Public Key" ec2-user@hostnameIP.compute-1.amazonaws.com`


##  4. Install Nginx web server

Use these commands :
`sudo yum upgrade` 
`sudo yum update`
`sudo yum install -y nginx` 
`sudo systemctl enable nginx`
`sudo systemctl start nginx`


5. Setting up DNS Record

   - Created A record
   - Name : root domain (@)
   - IPv4 addres -> MY EC2 Public IPv4 address




  6 . Final Result :

  <img width="1599" height="847" alt="image" src="https://github.com/user-attachments/assets/ebf4f692-608c-4a95-8d3b-dcb0426e98c7" />

  


## Challenges :

One challenge I encountered was understanding how SSL/TLS worked in practice .My site initially failed to load because Cloudflare's SSL/TLS setting was configured to "Full," which required valid SSL on the origin server. Switching the setting to "Flexible" resolved the issue by allowing HTTPS between the browser and Cloudflare without requiring SSL to be configured on the EC2 instance itself.
    

   

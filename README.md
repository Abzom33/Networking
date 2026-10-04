# Networking Project - Domain + EC2 + DNS
This project demonstates on how to deploy  an NGINX web server on an AWS EC2 instance and  connect it  to a custom domain via Cloudflare DNS.

Tools used :
- `Amazon Linux`
- `Cloudflare (DNS Setup)`
- `Nginx Web Server`
- `Security Groups`


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
 -  Add Key pair login (RSA) - This will be used for connecting your instance over SSH . 
 -  Security Groups :
     -  Allow SSH Traffic -> My IP address
     -  Allow HTTP -> port 80
    


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

- You can also add these to your EC2 User Data so that it can start automatically when the instance runs


## 5. Setting up DNS Record

   - Created A record
   - Name : root domain (@)
   - IPv4 addres -> Elastic IP
   -
     This is done so that the IP address remains static




  6 . Final Result :

  <img width="1599" height="847" alt="image" src="https://github.com/user-attachments/assets/ebf4f692-608c-4a95-8d3b-dcb0426e98c7" />

  

    

   

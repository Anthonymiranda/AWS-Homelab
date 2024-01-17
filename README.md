This is a cloud based cybersecurity homelab run on a linux EC2 instance and another Microsoft server 2022 EC2 instance.

The Homelab uses IAM for authentication & authorization through an AWS Organization setup where an umbrella account handles all other accounts under it for consolidated billing.

I used MFA for the root user and created admin accounts with admin rights to use for the daily use.

For the Microsoft Server 2022, I set up the VPC with a subnet that only allows inbound traffic through SSH through my own IP address
(image)

I had to download the RPD client for Macs and test the keys since my server instance was not allocating public ip addresses. After some throubleshooting, found out that the dsn was not set up to automatically assing public IP addresses which was a quick and easy fix
(image)

I used the key pairs i created on AWS to connect to the server
(image)

and here is a fully working Microsoft Server 2022 that I can work on remotely and access via RDP.
(Image)

For the Linux instance, I also set up a VPC with a subnet that only allows inbound traffic through SSH through my own IP address.
(image)

The VPC has an internet gateway which allows the assets inside the subnet to communicate out to the internet through it.
(image)

My chosen tested means of remote connection was putty though since I have a Mac, I first had to use the terminal to download putty through Macports.
I came into an issue where the putty GUI would not work. This was the reason I used Macports intead of homebrew version of Putty so I had to troubleshoot the issue. After some testing and research, I found out that if i used "Xquartz", the GUI would run find on my Mac so then I proceeded.
(Image)

And here is having full access to the Linux terminal remotely through putty via my Mac:
(Image)


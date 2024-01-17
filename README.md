This is a cloud based cybersecurity homelab run on a linux EC2 instance and another Microsoft server 2022 EC2 instance.

The Homelab uses IAM for authentication & authorization through an AWS Organization setup where an umbrella account handles all other accounts under it for consolidated billing.
![User created in Organizations via Identity center](https://github.com/Anthonymiranda/AWS-Homelab/blob/main/User%20created%20in%20Organizations.png)

I used MFA for the root user and created admin accounts with admin rights to use for the daily use.

For the Linux instance, I also set up a VPC with a subnet that only allows inbound traffic through SSH through my own IP address.
![VPC, Subnet, Route Tables]((https://github.com/Anthonymiranda/AWS-Homelab/raw/main/VPC%20w%20Subnet%20%26%20route%20tables.png)

The VPC has an internet gateway which allows the assets inside the subnet to communicate out to the internet through it.
![Internet facing gateway](https://github.com/Anthonymiranda/AWS-Homelab/blob/main/IG_homelab_vpc.png)

My chosen tested means of remote connection was putty though since I have a Mac, I first had to use the terminal to download putty through Macports.
I came into an issue where the putty GUI would not work. This was the reason I used Macports intead of homebrew version of Putty so I had to troubleshoot the issue. After some testing and research, I found out that if i used "Xquartz", the GUI would run find on my Mac so then I proceeded.
![Internet facing gateway](https://github.com/Anthonymiranda/AWS-Homelab/blob/main/Running%20Putty%20On%20Mac.png)

And here is having full access to the Linux terminal remotely through putty via my Mac:
![login through putty](https://github.com/Anthonymiranda/AWS-Homelab/blob/main/Putty%20connecting%20to%20EC2.png)

![login through putty](https://github.com/Anthonymiranda/AWS-Homelab/blob/main/Ec2%20connected%20via%20putty.png)

For the Microsoft Server 2022, I set up the VPC with a subnet that only allows inbound traffic through SSH through my own IP address
(image)

I had to download the RPD client for Macs and test the keys since my server instance was not allocating public ip addresses. After some throubleshooting, found out that the dsn was not set up to automatically assing public IP addresses which was a quick and easy fix
![rdp with key with mac](https://github.com/Anthonymiranda/AWS-Homelab/blob/main/connecting%20to%20Microsoft%20server%20with%20RDP.png)

I used the key pairs i created on AWS to connect to the server
![rdp with oay key connection](https://github.com/Anthonymiranda/AWS-Homelab/blob/main/connecting%20to%20rdp3.png)

and here is a fully working Microsoft Server 2022 that I can work on remotely and access via RDP.
![logged in windows](https://github.com/Anthonymiranda/AWS-Homelab/blob/main/Logged%20in%20to%20Windows%20Server%202022.png)



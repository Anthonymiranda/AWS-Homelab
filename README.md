<h2>Description</h2>
This is a cloud based cybersecurity homelab run on a linux EC2 instance and another Microsoft server 2022 EC2 instance.
<br>
<br>
<h2>Utilities Used</h2>

- AWS VPC 
- Subnets 
- Routing Tables
- Internet Gateways
- Microsoft Remote Connect for Mac
- Terminal
- Putty
- EC2
- Linux
- Microsoft Windows Server 2022

The Homelab uses IAM for authentication & authorization through an AWS Organization setup where an umbrella account handles all other accounts under it for consolidated billing.
<br>
<img width="1440" alt="User created in Organizations" src="https://github.com/Anthonymiranda/Azure-SIEM-Sentinel/assets/25447589/d9b762a6-106a-4c38-bd58-d4d8326d20eb">
<br>
<br>
I used MFA for the root user and created admin accounts with admin rights to use for the daily use.
<br>
<br>
For the Linux instance, I also set up a VPC with a subnet that only allows inbound traffic through SSH through my own IP address.
<img width="1440" alt="VPC w Subnet   route tables" src="https://github.com/Anthonymiranda/Azure-SIEM-Sentinel/assets/25447589/35c10ba7-6411-4c76-8eb1-60360a60d165">
<br>
<br>
The VPC has an internet gateway which allows the assets inside the subnet to communicate out to the internet through it.
<img width="1440" alt="IG_homelab_vpc" src="https://github.com/Anthonymiranda/Azure-SIEM-Sentinel/assets/25447589/fcfe4d84-117b-42ae-88ca-5e04ef655960">
<br>
<br>
My chosen tested means of remote connection was putty though since I have a Mac, I first had to use the terminal to download putty through Macports.
I came into an issue where the putty GUI would not work. This was the reason I used Macports intead of homebrew version of Putty so I had to troubleshoot the issue. After some testing and research, I found out that if i used "Xquartz", the GUI would run find on my Mac so then I proceeded.
<br>
<br>
And here is having full access to the Linux terminal remotely through putty via my Mac:
<img width="1440" alt="Putty connecting to EC2" src="https://github.com/Anthonymiranda/Azure-SIEM-Sentinel/assets/25447589/dd8bd1b7-a0ac-49b3-890d-51859be77e52">
<br>
<br>
<img width="1440" alt="Ec2 connected via putty" src="https://github.com/Anthonymiranda/Azure-SIEM-Sentinel/assets/25447589/dfe18b6e-0440-47cf-be46-f416d070aa7f">
<br>
<br>
For the Microsoft Server 2022, I set up the VPC with a subnet that only allows inbound traffic through SSH through my own IP address
<br>
<br>
I had to download the RPD client for Macs and test the keys since my server instance was not allocating public ip addresses. After some throubleshooting, found out that the dsn was not set up to automatically assing public IP addresses which was a quick and easy fix
<br>
<img width="1440" alt="connecting to Microsoft server with RDP" src="https://github.com/Anthonymiranda/Azure-SIEM-Sentinel/assets/25447589/1a0d7f5a-cd7e-4894-b0c1-a9c127101dd4">
<br>
<br>
I used the key pairs i created on AWS to connect to the server
<img width="1440" alt="connecting to rdp3" src="https://github.com/Anthonymiranda/Azure-SIEM-Sentinel/assets/25447589/d1b27173-15c4-42ab-b1ba-464f5504e1f1">
and here is a fully working Microsoft Server 2022 that I can work on remotely and access via RDP.
<img width="1440" alt="Logged in to Windows Server 2022" src="https://github.com/Anthonymiranda/Azure-SIEM-Sentinel/assets/25447589/b7a5d6da-2a4e-4b10-9ac5-72ecb173f788">



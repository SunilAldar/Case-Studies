# Case-Studies


# VPN set up using open vpn software for connecting private servers

A brief description of what this project does and who it's for


## Requirements
1) VPC with private and public servers.
2) Check SG for public server and allow UDP 1194 port. (for first time to check allow all traffic)


## Steps
1) Connect to public server and install open vpn software 
(refer this link for installation: https://github.com/Nyr/openvpn-install/blob/master/README.md )

Easiest way: use the community script.

sudo apt update && sudo apt upgrade -y
wget https://git.io/vpn -O openvpn-install.shchmod +x openvpn-install.sh
sudo ./openvpn-install.sh

The script will ask:

Protocol → UDP

Port → 1194

DNS → Google or default

Client name → e.g., somaling

When it finishes, it creates a client config file in current user's home directory:

/home/ubuntu/somaling.ovpn

2) Download the generated config file into your local machine.
If you face any issue while downloading it then try below step:
scp -i mykey.pem ubuntu@<VPN_SERVER_PUBLIC_IP>:/home/ubuntu/somaling.ovpn .

 

3) Now install openvpn client software  on your local machine. for this please refere below link:
https://openvpn.net/client/

4) Once openvpn client software instllation on your laptop finishes, open it and select brower option and provide downloaded config file and click on connect..

5) Now you can connect any private server from your personnel machine. Do one sanity for confirming this.

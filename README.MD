# AWS LIGHTSAIL DEPLOYEMENT:

After creating the instance, you can start directly with lightsail terminal or you can the lightsail's terminal on your pc terminal.

# 1.1  Lightsail's Terminal Access From local Machine Terminal:
To open your lightsail follow the following step:
    1. Downlaod the ssh key from lightsail, you can downlaod it .......... <br/>
    2. Open your terminal and paste `cp Download/private_key.pem ~/.ssh/` (This command will copy the file from download to .ssh folder)  <br/>
    3. paste `sudo nano  ~/.ssh/config` on your terminal.  <br/>
    4. add these line to your above config file.

    `Host lightsail-instance`  <br/>
    `HostName "your_ipv4_address"`  <br/>
    `User "bitnami"`  <br/>
    `IdentityFile ~/.ssh/your_private_key.pem`  <br/>

    That's it now you can access the light sail terminal from your pc's terminal by entering command `ssh lightsail-instance`


# 1.2 Ngnix Installation:
First, update the package list and upgrade installed packages:
`sudo apt update && sudo apt upgrade -y`
Run the following commands to install and start Nginx:
`sudo apt install nginx -y`
`sudo systemctl start nginx`
`sudo systemctl enable nginx`

if the ngnix isn't starting then change the port sometime it give you issues regarding the ports
so just copy and paste the following command and change the port from 80 to 8080.
`sudo nano /etc/nginx/sites-available/default`




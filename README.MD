# AWS LIGHTSAIL DEPLOYEMENT:

After creating the instance, you can start directly with lightsail terminal or you can the lightsail's terminal on your pc terminal.

# 1.1  Lightsail's Terminal Access From local Machine Terminal:
To open your lightsail follow the following step:
    1. Downlaod the ssh key from lightsail, you can downlaod it ..........
    2. Open your terminal and paste `cp Download/private_key.pem ~/.ssh/` (This command will copy the file from download to .ssh folder)
    3. paste `sudo nano  ~/.ssh/config` on your terminal.
    4. add these line to your above config file.

    `Host lightsail-instance
    HostName "your_ipv4_address"
    User "bitnami"
    IdentityFile ~/.ssh/your_private_key.pem`

    that's it now you can access the light sail terminal from your pc's terminal by entering command `ssh lightsail-instance`
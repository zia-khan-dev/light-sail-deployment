# AWS LIGHTSAIL DEPLOYMENT

After creating the instance, you can start directly with Lightsail's terminal or use Lightsail's terminal access from your local machine.

## 1.1 Lightsail's Terminal Access From Local Machine Terminal
To open your Lightsail instance, follow these steps:

1. Download the SSH key from Lightsail.
2. Open your terminal and paste the following command to move the key file to the `.ssh` folder:
   ```bash
   cp ~/Downloads/private_key.pem ~/.ssh/
   ```
3. Paste the following command to edit the SSH configuration file:
   ```bash
   sudo nano ~/.ssh/config
   ```
4. Add the following lines to your `config` file:
   ```
   Host lightsail-instance
       HostName your_ipv4_address
       User bitnami
       IdentityFile ~/.ssh/private_key.pem
   ```

That's it! Now you can access the Lightsail terminal from your PC's terminal by entering the command:
```bash
ssh lightsail-instance
```

## 1.2 Nginx Installation
First, update the package list and upgrade installed packages:
```bash
sudo apt update && sudo apt upgrade -y
```
Run the following commands to install and start Nginx:
```bash
sudo apt install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx
```

If Nginx doesn't start due to port issues, edit the default configuration file to change the port from 80 to 8080:
```bash
sudo nano /etc/nginx/sites-available/default
```

## 1.3 Database Installation
In this case, we are using PostgreSQL. Follow these steps to install it:

1. Run the following command to install PostgreSQL:
   ```bash
   sudo apt install postgresql postgresql-contrib -y
   ```

2. Start and enable PostgreSQL:
   ```bash
   sudo systemctl start postgresql
   sudo systemctl enable postgresql
   ```


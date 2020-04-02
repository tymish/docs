# Setting up AWS EC2 Ubuntu Server 18.04 for hosting Tymish Web Api

## Required software
* dotnet core runtime
* nginx web server
* Certbot SSL tool
* postgres database

### Dotnet Core Runtime 3.1
```bash
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb

sudo add-apt-repository universe
sudo apt update
sudo apt install apt-transport-https
sudo apt update
sudo apt install dotnet-runtime-3.1
dotnet --info                       # verify install
```


### Nginx Web Server 1.14.0
```bash
sudo apt install nginx
nginx -v    # verify install


sudo service nginx start
# open the public ip address in browser to verify service started
```

### Add SSL to Nginx

#### Install Certbot
```bash
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository ppa:certbot/certbot
sudo apt update

sudo apt install certbot python-certbot-nginx
```

#### Run Certbot
```bash
sudo certbot --nginx
```

#### Renew SSL
```bash
certbot renew
```

### PostgreSQL database

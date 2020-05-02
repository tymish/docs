# Setting up Ubuntu Server 18.04 for hosting Tymish Web Api

## Required software
* dotnet aspnetcore runtime
* nginx web server
* Certbot SSL tool
* postgres database

## Dotnet Core Runtime 3.1
```bash
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb

sudo add-apt-repository universe
sudo apt update
sudo apt install apt-transport-https
sudo apt update
sudo apt install dotnet-runtime-3.1
sudo apt install aspnetcore-runtime-3.1
dotnet --info                       # verify install
```


## Nginx Web Server 1.14.0
```bash
sudo apt install nginx
nginx -v    # verify install


sudo service nginx start
# open the public ip address in browser to verify service started
```

## Add SSL to Nginx

### Install Certbot
```bash
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository ppa:certbot/certbot
sudo apt update

sudo apt install certbot python-certbot-nginx
```

### Run Certbot
```bash
sudo certbot --nginx
```
`
### Renew SSL (Only do this if expired)
```bash
certbot renew
```

## PostgreSQL database

### Install
```bash
sudo apt update
sudo apt install postgresql postgresql-contrib
psql --version  # verify install
```

### Restore Db
Put this script on the server `create-db.sql`
```bash
psql -d Tymish -f create-db.sql
sudo -i -u postgres
psql
\l      # verify
```
### Create a db user that EF Core connection string will use
```bash
```

## Forward Nginx calls to Kestrel
### Modify `/etc/nginx/sites-available/default`
```
location / {
    proxy_pass         http://localhost:5000;
    proxy_http_version 1.1;
    proxy_set_header   Upgrade $http_upgrade;
    proxy_set_header   Connection keep-alive;
    proxy_set_header   Host $host;
    proxy_cache_bypass $http_upgrade;
    proxy_set_header   X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_set_header   X-Forwarded-Proto $scheme;
}
```

### Add Kestrel to `systemd` service manager
follow the link...
https://docs.microsoft.com/en-us/aspnet/core/host-and-deploy/linux-nginx?view=aspnetcore-3.1


## Server Details
app lives: `/var/www/tymish-api`
* `dotnet /var/www/tymish-api/WebApi.dll` to start Kestrel on the server

### Add additional SSH public keys to server
1. Create the public key with `ssh-keygen` 
2. Add the public key to new line in `~/.ssh/authorized_keys`
3. Use the private key to ssh in.

### Add the Kestrel service to systemd
Named: `/etc/systemd/system/kestrel-tymish-api.service`
```
[Unit]
Description=Tymish API running on .NET Core Kestrel

[Service]
WorkingDirectory=/var/www/tymish-api
ExecStart=/usr/bin/dotnet /var/www/tymish-api/WebApi.dll
Restart=always
# Restart service after 10 seconds if the dotnet service crashes:
RestartSec=10
KillSignal=SIGINT
SyslogIdentifier=dotnet-tymish-api
User=www-data
Environment=ASPNETCORE_ENVIRONMENT=production
Environment=DOTNET_PRINT_TELEMETRY_MESSAGE=false

# Secret environment
Environment=ConnectionStrings__TymishContext=""
Environment=ApiKeys__SendGrid=""

[Install]
WantedBy=multi-user.target
```

Enable the service
```bash
sudo systemctl enable kestrel-tymish-api.service
```
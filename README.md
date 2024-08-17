# Nextcloud Docker Compose Configuration  

A sample Docker Compose file for Nextcloud, Redis, and MariaDB.  

## Docker Networks Information  

* The Docker Compose file assumes you have already created Docker networks called ```Nextcloud```, ```Redis```, and ```MariaDB```. You can create a network before starting the container by executing the following command: ```docker network create <NETWORK_NAME>```  

## Environment Variables Configuration  

Create a file called ```.env``` in the same directory as the Docker Compose file containing the following properties:  

```env
NEXTCLOUD_VOLUMES=<DOCKER_BIND_MOUNTS_PATH>
MAIL_DOMAIN=<YOUR_DOMAIN.COM>
HOST=<YOUR_HOST.YOUR_DOMAIN.COM>
DB_USER=<YOUR_DB_USER>
DB_PASSWORD=<YOUR_DB_PASSWORD>
DB_ADMIN_PASSWORD=<YOUR_ADMIN_PASSWORD>
SMTP_HOST="<YOUR_SMTP_HOST>"
SMTP_USER="<YOUR_SMTP_USER>"
SMTP_PASSWORD="<YOUR_SMTP_PASSWORD>"
ADMIN_USER=<YOUR_ADMIN_USER>
ADMIN_PASSWORD="<YOUR_ADMIN_PASSWORD>"
TRUSTED_PROXIES="<YOUR_TRUSTED_PROXY_IP_RANGE>"
```

## Starting the container  

In your terminal, ```cd``` to the directory containing the ```docker-compose.yml``` and ```.env``` files. Run the following command: ```docker compose up -d```  
Your containers should be up and running and your Nextcloud instance be accessible on port 80 in the container. Setup your Docker Networks and reverse proxy accordingly.  

## Disclaimer  

This repository is provided as-is and is intended for informational and reference purposes only. The author assumes no responsibility for any errors or omissions in the content or for any consequences that may arise from the use of the information provided. Always exercise caution and seek professional advice if necessary.  

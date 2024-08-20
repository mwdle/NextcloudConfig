# Nextcloud Docker Compose Configuration  

A sample Docker Compose file for Nextcloud, Redis, and MariaDB.  

## Table of Contents  

* [Description](#nextcloud-docker-compose-configuration)  
* [Getting Started](#getting-started)  
* [License](#license)  
* [Disclaimer](#disclaimer)  

## Getting Started  

1. Clone the repository:  

    ```shell
    git clone https://github.com/mwdle/NextcloudConfig.git
    ```  

2. Create a folder on your system for Docker bind mounts / storing container files. The folder should have the following structure:  

    ```shell
    docker_volumes/
    ├── Nextcloud/
    │   ├── data/
    │   └── database/
    ```  

3. Create a file called `.env` in the same directory as the Docker Compose file containing the following properties:  

    ```properties
    DOCKER_VOLUMES=<PATH_TO_DOCKER_VOLUMES_FOLDER> # The folder created in the previous step.
    MAIL_DOMAIN="<YOUR_DOMAIN.COM>"
    HOST="<YOUR_HOST.YOUR_DOMAIN.COM>"
    DB_USER="<YOUR_DB_USER>"
    DB_PASSWORD="<YOUR_DB_PASSWORD>"
    DB_ADMIN_PASSWORD="<YOUR_ADMIN_PASSWORD>"
    SMTP_HOST="<YOUR_SMTP_HOST>"
    SMTP_USER="<YOUR_SMTP_USER>"
    SMTP_PASSWORD="<YOUR_SMTP_PASSWORD>"
    ADMIN_USER="<YOUR_ADMIN_USER>"
    ADMIN_PASSWORD="<YOUR_ADMIN_PASSWORD>"
    TRUSTED_PROXIES="<YOUR_TRUSTED_PROXY_IP_RANGE>"
    ```  

4. Open a terminal in the directory containing the docker-compose file.  
5. Create docker networks for the containers:  

    ```shell
    docker network create Nextcloud
    docker network create Redis
    docker network create MariaDB
    ```  

6. Start the containers:  

    ```shell
    docker compose up -d
    ```  

Your containers should be up and running and your Nextcloud instance be accessible on port 80 in the container. Attach your reverse proxy container to the previously created Nextcloud Docker Network and configure it accordingly.  

## License  

This project is licensed under the GNU General Public License v3.0 (GPL-3.0). See the [LICENSE](LICENSE.txt) file for details.  

## Disclaimer  

This repository is provided as-is and is intended for informational and reference purposes only. The author assumes no responsibility for any errors or omissions in the content or for any consequences that may arise from the use of the information provided. Always exercise caution and seek professional advice if necessary.  

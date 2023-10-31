# Project Name

## Description

This project sets up a multi-VM environment using Vagrant with various services and applications, including a database, Memcache, RabbitMQ, Nginx, and Tomcat. The environment is configured for development or testing purposes.

## Prerequisites

Before getting started, ensure you have the following software installed on your host machine:

- [Vagrant](https://www.vagrantup.com/)
- [VirtualBox](https://www.virtualbox.org/)

## Getting Started

### Vagrant Configuration

1. Clone this project repository to your local machine.

2. Open a terminal and navigate to the project directory.

3. Run the following command to start the VMs:

--"vagrant up"
### Backend Configuration
The backend.sh script performs the following actions:

### Installs and configures MariaDB (MySQL) with a database named "accounts."
Sets up a user "admin" with the password "admin123" and grants necessary privileges.
Restores a database dump from /vagrant/vprofile-repo/src/main/resources/db_backup.sql.
Configures MariaDB to allow remote connections.
Memcache Configuration
The memcache.sh script installs and configures Memcached to run on port 11211 with UDP support on port 11111. It also updates the firewall rules to allow Memcached traffic.

### RabbitMQ Configuration
The rabbitmq.sh script installs and configures RabbitMQ, creates a user "test" with the password "test," and grants administrator privileges. It also opens the necessary port for RabbitMQ.

### Nginx Configuration
The nginx.sh script installs Nginx, creates an Nginx server block configuration for proxying requests to the "app01" Tomcat instance, and restarts Nginx.

### Tomcat Configuration
The tomcat_ubuntu.sh script installs OpenJDK, Tomcat, and other necessary dependencies on an Ubuntu system.

The tomcat.sh script downloads Apache Tomcat, configures it, and deploys a WAR file from the "vprofile-project" repository. It also starts and enables Tomcat as a service.

### Usage
Access applications via the following IP addresses:
Nginx (web01): http://192.168.56.11
Tomcat (app01): http://192.168.56.12
RabbitMQ (rmq01): http://192.168.56.13
Memcache (mc01): http://192.168.56.14
MariaDB (db01): You can access it remotely after the script configuration.
License
This project is open-source and licensed under License Name, if applicable.

### Acknowledgments
Mention any sources, libraries, or individuals who contributed to this project.
### References
Include any relevant references or resources that users might find helpful.
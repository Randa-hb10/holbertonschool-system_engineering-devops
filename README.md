# holbertonschool-system_engineering-devops

This repository contains projects and tasks related to system engineering and DevOps.

The main goal of this repository is to understand how web infrastructure works, how users access websites, and how different infrastructure components communicate together.

## Project: Web Infrastructure Design

Directory:

```text
web_infrastructure_design
```

This project focuses on designing web infrastructures using whiteboard diagrams and explaining the role of each component.

## Learning Objectives

By the end of this project, I should be able to explain:

* What a server is
* What a domain name is
* What DNS is used for
* What type of DNS record is used for `www`
* What a web server does
* What an application server does
* What a database does
* How HTTP and HTTPS traffic works
* What a load balancer is
* What high availability means
* What a Single Point of Failure is
* How database replication works
* What firewalls are used for
* Why HTTPS is important
* What monitoring is used for
* How to scale a web infrastructure

## Tasks

### 0. Simple Web Stack

File:

```text
web_infrastructure_design/0-simple_web_stack
```

This task designs a simple one-server web infrastructure that hosts `www.foobar.com`.

The infrastructure includes:

* 1 server
* 1 domain name
* 1 DNS `www` record
* 1 web server: Nginx
* 1 application server
* 1 set of application files
* 1 MySQL database

Main issues with this infrastructure:

* Single Point of Failure
* Downtime during maintenance
* Cannot scale well with high traffic

### 1. Distributed Web Infrastructure

File:

```text
web_infrastructure_design/1-distributed_web_infrastructure
```

This task designs a distributed infrastructure using multiple servers.

The infrastructure includes:

* 1 load balancer: HAProxy
* 2 servers
* 2 Nginx web servers
* 2 application servers
* 2 sets of application files
* 2 MySQL databases
* Primary-Replica database replication

This improves availability and allows traffic to be distributed between servers.

Main issues:

* Load balancer is still a Single Point of Failure
* No firewall
* No HTTPS
* No monitoring

### 2. Secured and Monitored Web Infrastructure

File:

```text
web_infrastructure_design/2-secured_and_monitored_web_infrastructure
```

This task improves the distributed infrastructure by adding security and monitoring.

The infrastructure includes:

* 3 firewalls
* 1 SSL certificate
* HTTPS traffic
* 3 monitoring clients
* HAProxy load balancer
* 2 web/application/database servers
* MySQL Primary-Replica replication

This improves security and helps detect problems through monitoring.

Main issues:

* SSL termination at the load balancer can expose internal traffic
* Only one MySQL server accepts writes
* Having all components on the same servers can cause resource competition

### 3. Scale Up

File:

```text
web_infrastructure_design/3-scale_up
```

This task scales the infrastructure by separating components into different servers.

The infrastructure includes:

* 1 additional server
* 2 HAProxy load balancers configured as a cluster
* A dedicated web server
* A dedicated application server
* A dedicated database server
* A Primary-Replica MySQL setup

This improves scalability, availability, and performance.

## Key Concepts

### Server

A server is a computer that provides services, data, or resources to other computers over a network.

### Domain Name

A domain name is a human-readable address used to access a website instead of typing an IP address.

Example:

```text
www.foobar.com
```

### DNS

DNS translates domain names into IP addresses.

### Web Server

A web server such as Nginx receives HTTP/HTTPS requests from users and serves static files or forwards requests to the application server.

### Application Server

An application server runs the application logic and executes the code base.

### Database

A database stores and manages application data.

Example:

```text
MySQL
```

### Load Balancer

A load balancer distributes incoming traffic across multiple servers to improve availability and performance.

### Firewall

A firewall filters incoming and outgoing network traffic based on security rules.

### HTTPS

HTTPS encrypts traffic between the user and the website using an SSL/TLS certificate.

### Monitoring

Monitoring is used to track server health, application performance, logs, and system metrics.

## Author

Randa Baeshen


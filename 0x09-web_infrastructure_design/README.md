# Designing Web Infrastructure

## 0. Basic Web Stack

The objective here is to devise a straightforward web infrastructure to host the website "www.foobar.com." This infrastructure entails a solitary server housing the following components:

- Nginx Web Server
- Application Server
- Application Files (Your Code Base)
- MySQL Database

### 0.1 Design Overview and Rationale

[0. Basic Web Stack](https://github.com/BM-Ghost/alx-system_engineering-devops/blob/master/0x09-web_infrastructure_design/0-simple_web_stack): This document includes a link to the design image, fulfilling the specified criteria.

## 1. Distributed Web Infrastructure

This upgraded infrastructure employs three servers to host the website "www.foobar.com". Additional components include:

- Nginx Web Server
- Application Server
- HAproxy Load Balancer
- Application Files (Your Code Base)
- MySQL Database

### 1.1 Design Overview and Rationale

[1. Distributed Web Infrastructure](https://github.com/BM-Ghost/alx-system_engineering-devops/blob/master/0x09-web_infrastructure_design/1-distributed_web_infrastructure): This file provides a link to the design image, as per requirements.

## 2. Secure and Monitored Web Infrastructure

To bolster security, privacy, and monitoring capabilities, several supplementary components are incorporated into the existing three-server web infrastructure. These additions cater to enhanced protection, encrypted communication, and robust monitoring. The added components consist of:

- 3 Firewalls
- 1 SSL certificate for serving "www.foobar.com" via HTTPS
- 3 Monitoring Clients (Data collectors for Sumo Logic or alternative monitoring services)

### 2.1 Design Overview and Rationale

[2. Secure and Monitored Web Infrastructure](https://github.com/BM-Ghost/alx-system_engineering-devops/blob/master/0x09-web_infrastructure_design/2-secured_and_monitored_web_infrastructure): This document contains a link to the design image, meeting the specified criteria.

## 3. Scaling Up

This revised design incorporates significant modifications to the web infrastructure to enhance scalability, performance, and fault tolerance. The implemented changes include:

- Distributing components across individual servers
- Configuring both databases as primary databases for read and write operations
- Introducing an additional load balancer and configuring it as a cluster with the existing load balancer

### 3.1 Design Overview and Rationale

[3. Scaling Up](https://github.com/BM-Ghost/alx-system_engineering-devops/blob/master/0x09-web_infrastructure_design/3-scale_up): This file features a link to the design image, fulfilling the specified requirements.

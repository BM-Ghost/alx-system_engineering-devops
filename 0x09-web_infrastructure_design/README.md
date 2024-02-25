# Designing Web Infrastructure

## 0. Basic Web Stack

The objective here is to devise a straightforward web infrastructure to host the website "www.foobar.com." This infrastructure entails a solitary server housing the following components:

- Nginx Web Server
- Application Server
- Application Files (Your Code Base)
- MySQL Database

### 0.1 Design Overview and Rationale

[0. Basic Web Stack](./0-basic_web_stack): This document includes a link to the design image, fulfilling the specified criteria.

[Design Explanation](./0-Basic_Web_Stack.md): This section elucidates the infrastructure design and highlights any pertinent issues.

## 1. Distributed Web Infrastructure

This upgraded infrastructure employs three servers to host the website "www.foobar.com". Additional components include:

- Nginx Web Server
- Application Server
- HAproxy Load Balancer
- Application Files (Your Code Base)
- MySQL Database

### 1.1 Design Overview and Rationale

[1. Distributed Web Infrastructure](./1-distributed_web_infrastructure): This file provides a link to the design image, as per requirements.

[Design Explanation](./1-distributed_web_infrastructure.md): It delineates the infrastructure design and discusses any identified issues.

## 2. Secure and Monitored Web Infrastructure

To bolster security, privacy, and monitoring capabilities, several supplementary components are incorporated into the existing three-server web infrastructure. These additions cater to enhanced protection, encrypted communication, and robust monitoring. The added components consist of:

- 3 Firewalls
- 1 SSL certificate for serving "www.foobar.com" via HTTPS
- 3 Monitoring Clients (Data collectors for Sumo Logic or alternative monitoring services)

### 2.1 Design Overview and Rationale

[2. Secure and Monitored Web Infrastructure](./2-secure_and_monitored_web_infrastructure): This document contains a link to the design image, meeting the specified criteria.

[Design Explanation](./2-secure_and_monitored_web_infrastructure.md): This section elaborates on the infrastructure design and addresses any encountered issues.

## 3. Scaling Up

This revised design incorporates significant modifications to the web infrastructure to enhance scalability, performance, and fault tolerance. The implemented changes include:

- Distributing components across individual servers
- Configuring both databases as primary databases for read and write operations
- Introducing an additional load balancer and configuring it as a cluster with the existing load balancer

### 3.1 Design Overview and Rationale

[3. Scaling Up](./3-scaling_up): This file features a link to the design image, fulfilling the specified requirements.

[Design Explanation](./3-scaling_up.md): This section provides insight into the infrastructure design and addresses any identified issues.
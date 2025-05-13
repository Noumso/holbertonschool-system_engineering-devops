# 🌐 Web Infrastructure Design

This project focuses on designing scalable, secure, and highly available web infrastructure. We will progressively build and document a robust architecture, starting from a simple single-server stack to a fully distributed, secure, and monitored infrastructure.

## 📑 Table of Contents

- [Project Overview](#project-overview)
- [Learning Objectives](#learning-objectives)
- [Tasks](#tasks)
  - [Task 0: Simple Web Stack](#task-0-simple-web-stack)
  - [Task 1: Distributed Web Infrastructure](#task-1-distributed-web-infrastructure)
  - [Task 2: Secured and Monitored Web Infrastructure](#task-2-secured-and-monitored-web-infrastructure)
  - [Task 3: Scale Up](#task-3-scale-up)
- [Setup Instructions](#setup-instructions)
- [Diagrams](#diagrams)

## 🚀 Project Overview

The goal of this project is to design and implement various aspects of web infrastructure. Each task builds upon the last, starting from a simple, single-server web stack to a highly-available, fault-tolerant, and secure infrastructure with monitoring.

You will be designing and explaining:
- **Web Servers** (Nginx)
- **Application Servers**
- **Databases** (MySQL)
- **Load Balancers** (HAProxy)
- **Firewalls & HTTPS Security**
- **Monitoring Tools**

## 🎯 Learning Objectives

By the end of this project, you should be able to:

- 🖼️ **Design Web Stacks**: Understand and visually represent a simple web stack (LAMP).
- 🔒 **Explain Security & Redundancy**: Understand system redundancy and the risks of Single Points of Failure (SPOF).
- ⚖️ **Implement Load Balancing**: Know how to configure and deploy load balancers for optimal traffic distribution.
- 🔐 **Secure Infrastructure**: Use HTTPS, configure firewalls, and monitor traffic to secure the infrastructure.
- 📊 **Understand MySQL Clustering**: Learn how to set up Primary-Replica clusters for high availability.

## 🛠️ Tasks

### 🧑‍💻 Task 0: Simple Web Stack

Design a simple LAMP stack with one server. Host a website at `www.foobar.com`.

#### Requirements:
- **Domain Setup**: The domain `foobar.com` should point to `8.8.8.8`.
- **Server Configuration**:
  - Web Server: Nginx
  - Application Server: PHP
  - Database: MySQL

#### Explanation:
- 🌍 What is the role of the domain name (`foobar.com`)?
- 🔗 What DNS record type is used for `www`?
- 🔧 What does each component (web server, app server, DB) do?

#### Issues:
- ❌ SPOF (Single Point of Failure)
- ⚠️ Downtime during maintenance (server restart)
- 📉 No scalability for high traffic

---

### ⚙️ Task 1: Distributed Web Infrastructure

Upgrade to a distributed web infrastructure using two servers and a load balancer.

#### Requirements:
- **Infrastructure**:
  - 1 Load Balancer (HAProxy)
  - 2 Servers, each with:
    - Nginx Web Server
    - Application Server (PHP)
    - MySQL Database (Primary-Replica)

#### Explanation:
- 🔄 **Why add a load balancer?** What distribution algorithm are you using?
- 🔄 **Active-Active vs Active-Passive** load balancing.
- 💻 **Primary-Replica MySQL Cluster**: How does it improve availability?

#### Issues:
- 🔒 Security concerns (no HTTPS, no firewall)
- 📉 No monitoring in place
- 🚧 SPOF still exists (load balancer and MySQL Primary)

---

### 🔒 Task 2: Secured and Monitored Web Infrastructure

Secure the infrastructure, enable HTTPS, and add monitoring.

#### Requirements:
- **Enhancements**:
  - 🔐 3 Firewalls
  - 🌐 SSL Certificate for HTTPS
  - 📊 3 Monitoring Clients (e.g., Sumologic)

#### Explanation:
- 🔐 **Why firewalls?** What role do they play in securing your infrastructure?
- 🌐 **Why HTTPS**: Why is encrypting traffic important?
- 📈 **How does monitoring work?** How do you monitor QPS (queries per second) on the web server?

#### Issues:
- 🛑 SSL termination at the load balancer: Risks and considerations
- 🔄 **Single MySQL write node**: Impact on performance and availability
- 📊 **Homogeneous infrastructure**: What’s the problem with identical components on all servers?

---

### 📈 Task 3: Scale Up

Split components (web, app, database) onto separate servers and add a second load balancer for better performance.

#### Requirements:
- **Infrastructure**:
  - Second load balancer (HAProxy)
  - Separate servers for web, application, and database components

#### Explanation:
- ⚙️ **Why separate components?** What’s the benefit in terms of scalability?
- 🚀 **How does this setup increase availability and fault tolerance?**

---
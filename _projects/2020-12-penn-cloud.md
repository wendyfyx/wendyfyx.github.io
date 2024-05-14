---
title: PennCloud
layout: post
date: 2020-12-21
tagline: Course project for CIS 505 Software Systems @Penn
description: A distributed cloud platform with email service and file storage built in C++
---

This is a class project for CIS 505 Software Systems (Fall 2020) at University of Pennsylvania.

:cloud: PennCloud :cloud: is a distributed cloud platform, with webmail service similar to Gmail, and a storage service similar to Google Drive. This project is built in C++, with [Protobuf](https://developers.google.com/protocol-buffers) used for data serialization, [gRPC](https://grpc.io/) used for communication between components and React for frontend applications. See each component and its features below:

### Frontend
- Clients are directed to one of multiple **frontend servers** through a load balancer. Each frontend server periodically send a ping message to the **frontend load balancer** which keeps track of all frontend servers and their status. 
- The frontend servers provide interfaces for webmail service and storage service for each user account. 
- A special **admin console** page shows status of all frontend, backend servers and a way to view all key-value pairs stored in the BigTable.

### Backend
Each frontend server also serves as a **backend client** with an interface to access storage operations in the **backend servers**. To make our application more robust, we built support for data replication, load balancing, checkpointing and recovery.
- **Health check**: A single **backend master** node keeps track of all backend server status (using a pinging service similar to frontend load balancer keeping track of frontend servers).
- **Load Balancing**: Each new backend client (frontend server) is assigned a backend server with the least load (fewest data entries). The backend client caches the address of the backend server for further requests.
- **Quorum Replication**: We implement quorum replication for stronger fault tolerance. To minimizing losing data in case a server dies, we write data to all healthy servers; and for faster read, we contact half of the healthy servers to get the data.
- **Local Checkpointing & Recovery**: The backend server node has its own BigTable storage, all changes are in memory and stored in a log file for each operation. It periodically dumps key-value pairs in memory to the local storage file (checkpointing). When a node fails, the backend master sends the failed node's address to a healthy node who sends its recovery file.

<figure style="margin-top:1em; margin-bottom:1em; display: flex; flex-direction: column; align-items: center;">
    <img src="/files/projects/penncloud.png" alt="DGCCA Architecture" style="width:100%;"/>
    <figcaption style="font-style: italic;">PennCloud Design</figcaption>
</figure>
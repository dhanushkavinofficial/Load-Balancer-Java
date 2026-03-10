# Load-Balancer-Java
Load Balancer – Low Level Design (Java)
Overview

This project demonstrates a Low-Level Design (LLD) implementation of a Load Balancer using Java.

A Load Balancer distributes incoming network traffic across multiple backend servers to ensure:

High availability

Fault tolerance

Better performance

Scalability

This implementation simulates a Round Robin Load Balancing algorithm.

System Design Concept

A Load Balancer acts as a traffic controller between clients and backend servers.

Client Requests
       |
       v
   Load Balancer
    /    |    \
Server1 Server2 Server3

The Load Balancer distributes requests sequentially across available servers.

Features

✔ Round Robin Load Balancing
✔ Thread-safe server selection
✔ Health check simulation
✔ Dynamic server registration
✔ Simple request dispatcher
✔ Object-Oriented Design

Project Structure
LoadBalancer.java
 ├── Server
 ├── RoundRobinBalancer
 ├── ClientRequest
 ├── RequestDispatcher
 └── Main Simulation
Class Design
1️⃣ Server

Represents a backend server.

Attributes:

ip
port
health status

Methods:

getAddress()
isHealthy()
setHealth()
2️⃣ RoundRobinBalancer

Core component responsible for selecting the next server.

Uses:

AtomicInteger

This ensures thread-safe request distribution.

Algorithm:

index % totalServers
3️⃣ ClientRequest

Represents incoming client traffic.

Example:

Request-1
Request-2
Request-3
4️⃣ RequestDispatcher

Routes incoming requests to the selected server.

Flow:

ClientRequest -> LoadBalancer -> Selected Server
Load Balancing Algorithm

This implementation uses Round Robin.

Example:

Request1 → Server1
Request2 → Server2
Request3 → Server3
Request4 → Server1
Request5 → Server2

Advantages:

Simple

Fair distribution

Low overhead

Sample Output
Routing request: Request-1 -> Server: 192.168.1.10:8080
Routing request: Request-2 -> Server: 192.168.1.11:8080
Routing request: Request-3 -> Server: 192.168.1.12:8080
Routing request: Request-4 -> Server: 192.168.1.10:8080
Routing request: Request-5 -> Server: 192.168.1.11:8080
Possible Enhancements

This project can be extended with real system design features:

Health Check Monitoring

Automatically remove unhealthy servers.

Weighted Round Robin

Servers with higher capacity receive more requests.

Least Connections

Route requests to server with fewer active connections.

Consistent Hashing

Useful for distributed caching systems.

Rate Limiting

Protect servers from overload.

Real World Examples

Load balancers are used in:

Netflix

Amazon

Google Cloud

Kubernetes

NGINX

AWS Elastic Load Balancer

Technologies Used

Java

OOP Design

Concurrency (AtomicInteger)

Learning Outcomes

This project helps understand:

Low Level System Design

Traffic distribution algorithms

Thread-safe programming

Backend architecture design

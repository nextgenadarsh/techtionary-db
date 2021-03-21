# AWS Networking and VPC

- [AWS Networking and VPC](#aws-networking-and-vpc)
  - [VPC](#vpc)
  - [Subnets](#subnets)
  - [Internet Gateway (IGW)](#internet-gateway-igw)
  - [Route Table](#route-table)
  - [Network Access Control List (NACL)](#network-access-control-list-nacl)
  - [Security Groups](#security-groups)
  - [NAT Gateway](#nat-gateway)
  - [Bastion Hosts](#bastion-hosts)
  - [Virtual Private Network (VPN)](#virtual-private-network-vpn)
  - [Direct Connect Connection](#direct-connect-connection)
  - [VPC Peering](#vpc-peering)
  - [AWS Transit Gateway](#aws-transit-gateway)

## VPC

- is an isolated segment of the AWS infrastructure allowing you to provision your cloud resources
- 5 VPC per region per account allowed
- IP ranges from /16 to /28

## Subnets

- allows you to segment your VPC CIDR block forming smaller network segments across multiple availability zones
- Segmentation allows you to isolate, organize and manage resources in addition to helping you implement resilience and high availability
- subnet can be private or public
- each subnet has one route table with local or gateway routes

## Internet Gateway (IGW)

- An AWS managed component attached to your VPC providing a connection between your isolated VPC and outside world
- For a public subnet to access internet a route must be added with the target defined as the IGW.

## Route Table

- Enables you to configure where and how to route your network traffic based on its destination via different targets, such as IGW, NAT Gateways and Virtual Private Gateways

## Network Access Control List (NACL)

- Effectively acts as a logical firewall providing network level security operating at the subnet layer
- A way to control in and out traffic from a **subnet**
- A subnet can be associated to only one NACL
- One NACL can be associate to multiple subnet
- It is stateless by design
- The NACL rule base allows you to define both ingress and egress traffic based on protocols
- Each rules has an action associated that will either allow or deny traffic

## Security Groups

- Virtual firewalls that operates at the instance layer
- Rules within the rule base are considered 'allowed' as security groups do not offer a 'deny' function like NACL.
- A way to control in and out traffic from an **instance**
- It is stateful means you don't have to configure specific rule to allow return traffic from the request

## NAT Gateway

- Allows private instances located within a private subnet to access the internet to download patch updates and maintenance
- It prevents inbound connects that are initiated from the internet, protecting your private resources
- It is located within public subnet.
- It is managed instance provided by AWS.
- We add the route for internet to route table in private subnet to redirect traffic to NAT gateway

## Bastion Hosts

- A secure and hardened instance that resides inside public subnet of your VPC
- It has very restrictive security controls allowing only restricted inbound connections from known and trusted IP addresses using encrypted protocols such as SSH or RDP
- It acts as the 'Jump Server' allowing engineers to SSH or RDP to private instances
- A security group is applied to Bastion host to allow only inbound access to host using SSH
- A security group is applied to private subnets instance to allow only inbound access to instances from Bastion host's security group
- A user can use the `SSH Agent Forwarding` to connect to private instance using the private key stored on his machine 

## Virtual Private Network (VPN)

- A connection allowing 2 remote networks to securely connect to each other across internet
- A VPN can connect your remote office to your VPC

## Direct Connect Connection

- Allows you to connect your VPC to your remote office or data center across dedicated and secure infrastructure rather than the internet

## VPC Peering

- Allows you to connect 2 VPCs together using the internal AWS infrastructure as if they were on the same network
- Peered VPC are not allowed to have overlapping CIDR blocks
- It provides 1:1 connection and does not allow transitive peering

## AWS Transit Gateway

- Allows you to perform a 1:Many relationship with your VPCs in addition to your remote networks
- It acts as the central hub within your network allowing all VPCs and remote offices to connect
- It simplifies multiple peering connections and reduce overall connectivity from remote locations to your VPCs


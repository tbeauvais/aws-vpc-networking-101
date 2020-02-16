# AWS VPC Networking 101
This repo will walk you through setting up a fully functional and reasonably simple AWS VPC. I have tried to make it as complete as possible without making it overly complicated.

## Overview
In this example, we will create a VPC with two subnets. One subset will be private and one public. The scenario I'm trying to simulate is a network with internal (non-public), and external facing services. These services can range from micro-services to a backend datastore. To keep the example as simple as possible, we will be simulating the services using two Apache HTTP web servers.  For example, a request from the public internet is allowed over HTTP port 80 to the Apache server in the public subnet, and the public server is permitted to access the Apache server in the private subnet. 
![aws overview](doc/aws_network_overview.jpeg)


## VPC Details
When creating a VPC, one of the first things you will need to decide is the private IP address range. The private IP address range is specified using CIDR notation (Classless Inter-Domain Routing). For example, in this exercise, we will be using 10.0.0.0/16, which gives us 65,536 total addresses (-5 reserved by AWS) gives us 65,531 available IP addresses in our VPC. This VPC IP range will then be subdivided amongst each of the subnets.


![aws details](doc/aws_vpc_simple_network.jpeg)

- VPC - Amazon Virtual Private Cloud (VPC) is a virtual network that you define in AWS to run your AWS resources such as EC2 instances.
- Subnet - A subnet allows you to divide up a range of IP addresses within your VPC
- Route Tables - A routing table contains a set of rules that direct network traffic from your subnet or gateway.
- Security Group -
- Network ACL -
- Internet Gateway -
- NAT Gateway -

## Creating the VPC Network


## Cleaning up the VPC Network

## Resources
https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html
https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html

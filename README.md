# AWS VPC Networking 101
This repo will walk you through setting up a fully functional and reasonably simple AWS VPC. I have tried to make it as complete as possible without making it overly complicated.

## Overview
In this example, we will create a VPC with two subnets. One subset will be private and one public. The scenario I'm trying to simulate is a network with internal (non-public), and external facing services. These services can range from micro-services to a backend datastore. To keep the example as simple as possible, we will be simulating the services using two Apache HTTP web servers.  For example, a request from the public internet is allowed over HTTP port 80 to the Apache server in the public subnet, and the public server is permitted to access the Apache server in the private subnet. 
![aws overview](doc/aws_network_overview.jpeg)


## VPC Details
When creating a VPC, one of the first things you will need to decide is the private IP address range. The private IP address range is specified using CIDR notation (Classless Inter-Domain Routing). For example, in this exercise, we will be using 10.0.0.0/16, which gives us 65,536 total addresses in our VPC. This VPC IP range will then be subdivided amongst each of the subnets.

Note - If you are unfamiliar with subnetting, I suggest you go through the [Subnetting Demystified](https://www.youtube.com/watch?v=cdNsiz12aCY) video series. 

The subnet will futher divide the VPC address ranges to create smaller networks that can be individually managed. As mentioned previously we will be creating two subnets within the VPC. Again we will need to use CIDR notation to specifiy the subnet ranges. These ranges must be withing the VPC 10.0.0.0/16 range. The fist subnet will use 10.0.0.0/24, which gives us 256 addresses with a range of 10.0.0.0-10.0.0.255. The second subnet will use 10.0.1.0/24, which also gives us 256 addresses with a range of 10.0.1.0 - 10.0.1.255. The 256 addresses in each subnet are reduced by five due to AWS reserved addresses. The subnet address ranges cannot overlap within the VPC.   
![aws subnets](doc/aws_subnets.jpeg)

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

# AWS VPC Networking 101

This repo will walk you through setting up a fully functional and reasonably simple AWS VPC. I have tried to make it as complete as possible without making it overly complicated.

## Overview
In this example, we will create a VPC with two subnets. One subset will be private and one public. The scenario I'm trying to simulate is a network where you have internal (non-public), and external facing services. These services can range from micro-services to a datastore. To keep the example simple, we will be simulating the services using two Apache HTTP servers.  
![aws overview](doc/aws_network_overview.jpeg)


## VPC Details
![aws details](doc/aws_vpc_simple_network.jpeg)

# AWS Blue-Green Deployment

## Project Overview

This project demonstrates the Blue-Green Deployment approach using AWS infrastructure. The objective is to understand how separate application environments can support safer releases and controlled traffic switching.

## AWS Services

* Amazon EC2
* Application Load Balancer (ALB)
* Target Groups
* Amazon VPC
* Security Groups

## Architecture

The project uses separate Blue and Green application environments hosted on EC2 instances. An Application Load Balancer routes incoming HTTP traffic to the configured target group.

## Key Activities

* Configured EC2 instances for application environments.
* Set up an Application Load Balancer and target groups.
* Practiced target health checks and traffic switching.
* Applied VPC, subnet, and security group concepts.
* Explored rollback procedures for deployment recovery.

## Project Documentation

Screenshots and deployment steps are included in this repository.

## Learning Outcomes

* Understanding AWS load balancing.
* Learning Blue-Green Deployment concepts.
* Practicing cloud networking and application availability concepts.

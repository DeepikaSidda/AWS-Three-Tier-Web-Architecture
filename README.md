# Deploying a Scalable Three-Tier Web Architecture on AWS — Complete Guide

## Follow the Full Step-by-Step Guide
For a detailed, step-by-step walkthrough of this entire architecture, follow the full Medium blog here:  
👉 **https://medium.com/@siddadeepika/deploying-a-scalable-three-tier-web-architecture-on-aws-complete-guide-0d838e448ef4**

## Pre-requisites:
1. An AWS account. If you don’t have an AWS account, follow the instructions [here](https://aws.amazon.com/console/) and click on “Create an AWS Account” button in the top right corner to create one.  
2. IDE or text editor of your choice.

## Architecture Overview
![Architecture Diagram](https://github.com/aws-samples/aws-three-tier-web-architecture-workshop/blob/main/application-code/web-tier/src/assets/3TierArch.png)

In this architecture, a public-facing Application Load Balancer forwards client traffic to our web tier EC2 instances.  
The web tier is running **Nginx webservers** that:
- Serve a **React.js frontend**, and  
- Redirect API calls to the application tier’s **internal-facing load balancer**

The **internal ALB** then forwards traffic to the **application tier**, which is built using **Node.js**.

The application tier interacts with an **Aurora MySQL Multi-AZ** database to perform read/write operations and returns the data to the web tier.

Load balancing, health checks, and autoscaling groups are created at each layer to ensure **high availability**, **fault tolerance**, and **scalability** of the entire architecture.

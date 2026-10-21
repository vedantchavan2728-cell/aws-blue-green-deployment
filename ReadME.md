# 🚀 AWS Blue-Green Deployment

### A Cloud Deployment Project Using AWS EC2, Application Load Balancer & Target Groups

![AWS](https://img.shields.io/badge/Cloud-AWS-orange)
![EC2](https://img.shields.io/badge/Compute-EC2-yellow)
![Load Balancer](https://img.shields.io/badge/Networking-Application%20Load%20Balancer-blue)
![Deployment](https://img.shields.io/badge/Strategy-Blue--Green-brightgreen)
![Status](https://img.shields.io/badge/Status-Hands--On%20Project-success)

## 📌 Project Overview

This project demonstrates the implementation of a **Blue-Green Deployment architecture on Amazon Web Services (AWS)**.

Blue-Green Deployment is a release strategy that uses two separate application environments: Blue (current environment) and Green (new environment). Traffic can be switched between these environments to support controlled releases and reduce deployment downtime.

The project uses Amazon EC2 instances, an Application Load Balancer (ALB), and separate Target Groups to explore traffic routing, health checks, and deployment management.

## 🎯 Project Objectives

* Understand the Blue-Green Deployment strategy.
* Deploy application environments using Amazon EC2.
* Configure an Application Load Balancer.
* Create and configure separate Target Groups.
* Understand target health checks and traffic routing.
* Configure Security Groups for controlled network access.
* Explore how traffic switching can support safer application releases.

## 🏗️ Architecture

The project follows this high-level architecture:

```text
                  Users / Clients
                         |
                         v
              Application Load Balancer
                         |
                Listener / Routing Rules
                         |
                 +-------+-------+
                 |               |
                 v               v
          Blue Target Group  Green Target Group
                 |               |
                 v               v
            Blue EC2         Green EC2
          (Environment A)  (Environment B)
```

**Traffic Flow:** Users access the application through the Application Load Balancer. The listener forwards requests to the configured target group, which routes traffic to registered and healthy EC2 instances.

The active target group can be changed as part of a controlled deployment process.

> Note: This diagram represents the conceptual architecture. The exact listener rules, target group configuration, and traffic-switching method depend on the deployed setup.

## 🛠️ AWS Services Used

| Service                   | Purpose                                                             |
| ------------------------- | ------------------------------------------------------------------- |
| Amazon EC2                | Hosts the application environments                                  |
| Application Load Balancer | Receives HTTP requests and routes traffic                           |
| Target Groups             | Group registered application instances                              |
| Security Groups           | Control inbound and outbound traffic                                |
| Amazon VPC                | Provides the network environment                                    |
| EC2 Health Checks         | Help verify application instance health through target group checks |

## 🔄 How Blue-Green Deployment Works

### 1. Blue Environment

The Blue environment represents the current application environment.

* Launch and configure the EC2 instance.
* Deploy the application.
* Register the instance with the Blue Target Group.
* Verify application availability.

### 2. Green Environment

The Green environment represents the new application environment.

* Launch and configure another EC2 instance.
* Deploy the new application version.
* Register the instance with the Green Target Group.
* Verify that the application is working correctly.

### 3. Application Load Balancer

Configure an Application Load Balancer to receive incoming requests.

* Create a listener.
* Configure the appropriate forwarding action.
* Associate the required target groups.
* Verify target health and application connectivity.

### 4. Traffic Switching

Switch traffic to the intended environment using the configured listener action or routing rules.

Before switching traffic, verify that the destination environment is healthy and the application is accessible.

### 5. Validation

After switching traffic:

* Open the application using the load balancer DNS name.
* Verify that requests reach the intended environment.
* Check target group health.
* Confirm that the application responds correctly.

## 📸 Project Screenshots

Screenshots are available in the [`screenshots/`](screenshots/) directory.

### EC2 Instances

![EC2 Instances](screenshots/ec2-instances.png)

### Application Load Balancer

![Application Load Balancer](screenshots/load-balancer.png)

### Target Groups

![Target Groups](screenshots/target-group.png)

> Make sure the screenshot filenames match the actual files in the `screenshots/` directory. Update these paths if your filenames are different.

## 🔐 Security Considerations

* Allow only the network traffic required by the application.
* Restrict SSH access to trusted IP addresses.
* Configure appropriate Security Group rules for the load balancer and EC2 instances.
* Never commit AWS access keys, private keys, passwords, or other secrets to GitHub.
* Review AWS resources and delete unused resources after testing to avoid unnecessary charges.

## 📚 Key Learnings

Through this project, I gained practical exposure to:

* AWS EC2 instance configuration.
* Application Load Balancer setup.
* Target Group configuration and health checks.
* AWS networking and Security Groups.
* Application traffic routing.
* Blue-Green Deployment concepts.
* Troubleshooting cloud deployment connectivity.

## 🚀 Future Improvements

* Automate application deployments using Jenkins.
* Build a CI/CD pipeline for controlled releases.
* Use Infrastructure as Code with Terraform.
* Add application monitoring and alerting.
* Implement automated validation and rollback workflows.

## 👨‍💻 Author

**Vedant Chavan**

Computer Engineering Graduate | Aspiring DevOps & Cloud Engineer

* GitHub: [vedantchavan2728-cell](https://github.com/vedantchavan2728-cell)
* LinkedIn: [Connect on LinkedIn](https://www.linkedin.com/in/vedant-chavan28/?isSelfProfile=true)

## ⭐ Acknowledgements

This project was built as part of my hands-on learning journey in AWS Cloud Computing and DevOps Engineering.

If you find this project useful, feel free to explore the repository and share your feedback!

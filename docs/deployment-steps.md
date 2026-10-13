# AWS Blue-Green Deployment — Step-by-Step Guide

## Step 1: Create EC2 Instances

Launch two EC2 instances:

* Blue Environment: `blue-green-blue`
* Green Environment: `blue-green-green`

Install and configure Nginx on both instances. Configure each environment to display a different page so that the active environment can be identified.

## Step 2: Create Target Groups

Create two target groups:

* `blue-target-group`
* `green-target-group`

Configure the target groups to use the correct protocol and port for the application. Register the corresponding EC2 instances and verify their health status.

## Step 3: Create the Application Load Balancer

Create an Application Load Balancer named `blue-green-alb`.

Configure its networking and security group. Select the appropriate subnets and configure the listener to forward traffic to the blue target group initially.

## Step 4: Test the Blue Environment

Open the Application Load Balancer DNS name in a browser.

Verify that the blue application's page is displayed and that the target group reports healthy targets.

## Step 5: Prepare the Green Environment

Verify that the green EC2 instance is running Nginx and serving the green application's page.

Check that the green target group reports healthy targets before switching traffic.

## Step 6: Switch Traffic

Modify the load balancer listener's forwarding action to use `green-target-group`.

Open or refresh the load balancer DNS address and verify that the green application's page is displayed.

## Step 7: Verify the Deployment

Confirm that the selected target group is healthy and that the application is accessible through the load balancer.

The blue environment can be retained as a rollback option while it is still available and properly configured.

## Important Notes

* AWS resource names may differ if resources were created with different names.
* Security groups must allow the required application traffic.
* Check target health before switching traffic.
* AWS resources may incur charges. Delete resources when they are no longer needed.

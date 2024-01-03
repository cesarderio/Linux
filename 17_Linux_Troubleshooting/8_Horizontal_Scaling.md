# Horizontal Scaling of Linux Using Load Balancing in Microsoft Azure

<br>

## Concept of Horizontal Scaling

- **Horizontal Scaling**: Adding or removing Linux-based virtual machines to handle varying workloads.
- Employing load balancers to distribute workload across multiple VMs effectively.

<br>

## Creating Load Balancer Configuration

- **Initial Setup**: In the Azure portal, navigating to Virtual machines, ensuring VMs are running.
- **Load Balancer Creation**:
  - Searching for Load Balancer in the marketplace.
  - Assigning the load balancer to a resource group.
  - Naming the load balancer and selecting region and SKU.
  - Opting for Public IP for frontend configuration.
  - Defining the frontend IP configuration.
  - Creating backend pools with Ubuntu Linux VMs.

<br>

## Setting Up Frontend and Backend Configurations

- Configuring frontend with a new public IP.
- Adding backend pools with selected Ubuntu VMs.
- Setting inbound rules for load balancing (e.g., configuring ports and health probes).

<br>

## Deploying and Managing the Load Balancer

- Reviewing and creating the load balancer.
- Verifying frontend IP configurations and backend pools post-deployment.
- Option to manually scale by adding or removing VMs.

<br>

## Autoscaling in Azure

- **Virtual Machine Scale Set**: Allows for automated scaling based on predefined policies.
- **Scaling Policy Configuration**: Setting initial instance count, maximum number of instances, and CPU utilization triggers.
- **Azure App Service**: Provides automatic scaling with optional fine-grained control.

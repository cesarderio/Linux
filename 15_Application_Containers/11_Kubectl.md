# Basic Kubernetes Management with kubectl in Microsoft Azure

<br>

## Introduction

- **Focus**: Demonstrating basic Kubernetes management using the `kubectl` command in Azure.
- **Flexibility**: Kubernetes can be installed on-premises or deployed in cloud environments like Azure.

<br>

## Steps in Managing Kubernetes Cluster in Azure

<br>

### Accessing Kubernetes Clusters in Azure

1. **Azure Portal Navigation**: Start by logging into the Microsoft Azure portal.
2. **Exploring Resources**: Go to the "All resources" view and search for Kubernetes-related resources.

<br>

### Connecting to Kubernetes Cluster

1. **Selecting the Cluster**: Identify the Kubernetes cluster service object (e.g., `myakscluster178`).
2. **Establishing Connection**: Click the "Connect" button in the cluster's overview page to view connection instructions.

<br>

### Using Azure Cloud Shell for Kubernetes Management

1. **Launching Cloud Shell**: Access Cloud Shell via the Azure portal for command-line tools.
2. **Acquiring Cluster Credentials**: Use `az aks get-credentials` to authenticate the connection to the Kubernetes cluster.

<br>

### Managing Cluster with kubectl

1. **Listing Nodes**: Use `kubectl get nodes` to display active nodes in the cluster.
2. **Creating YAML Config File**: Utilize `nano` to create an `app1.yaml` file, defining the deployment details.
3. **Applying Configuration**: Deploy the configuration to the cluster using `kubectl apply -f app1.yaml`.

<br>

### Additional Kubernetes Commands

1. **Viewing Pods**: Use `kubectl get pods --all-namespaces` to list all pods, including newly created ones.
2. **Showing Labels**: To view more details, run `kubectl get pods --show-labels`.

<br>

### Copying Files to Pods

- **File Transfer**: Use `kubectl cp` to copy local files into the running container within a pod.

<br>

## Conclusion

Kubernetes management in Microsoft Azure, using the `kubectl` command, provides a robust and flexible environment for deploying and managing containerized applications. The process involves navigating the Azure portal, connecting to the Kubernetes cluster, and utilizing various `kubectl` commands to manage the cluster effectively. This approach is suitable for large-scale applications, whether for high-traffic websites or extensive data analytics.

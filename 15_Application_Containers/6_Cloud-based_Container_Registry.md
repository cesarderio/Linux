# Creating an Azure Container Registry and Pushing Docker Images

<br>

## Setting Up Azure Container Registry

<br>

### Accessing Azure Portal

1. **Login**: Sign in to the Microsoft Azure portal with an existing account.
2. **Resource Creation**: Click "Create a resource" and search for "Azure Container Registry."

<br>

### Creating the Registry

1. **Selecting Container Registry**: Choose "Container Registry" from Microsoft.
2. **Configuration**:
   - **Resource Group**: Assign a resource group (e.g., stdcontainerregistry172).
   - **Registry Name**: Assign a name, automatically appending `.azurecr.io` DNS suffix.
   - **Location**: Select a geographical location (e.g., East US).

<br>

### Network and Encryption Settings

1. **Networking**: Choose between public and private access; standard SKU options may be limited.
2. **Encryption**: Choose to enable or disable customer-managed keys.

<br>

### Finalizing Registry Creation

1. **Review and Create**: Final check before creating the registry.
2. **Deployment Confirmation**: Once created, access the registry via "Go to resource" or "All resources."

<br>

## Preparing for Docker Image Push

<br>

### Docker Host Verification

1. **Check Docker Status**: Use `sudo service docker status` on the local host to confirm Docker is active and running.
2. **Docker Login**: Use the Azure portal to enable the Admin user in "Access keys" and then login using `sudo docker login [registry_name].azurecr.io`.

<br>

### Tagging Local Docker Images

1. **Tagging for Registry**: Use `sudo docker tag [local_image_name][registry_name].azurecr.io/[new_image_name]` to tag the local Docker image for the registry.
2. **View Tagged Images**: Confirm the newly tagged image with `sudo docker images`.

<br>

## Pushing Image to Azure Container Registry

<br>

### Uploading Image

1. **Docker Push Command**: Use `sudo docker push [registry_name].azurecr.io/[new_image_name]` to upload the image to Azure Container Registry.
2. **Verifying Upload**: Check the Azure portal under "Repositories" to see the uploaded image (e.g., `my-alpine`).

<br>

## Conclusion

This process outlines how to create an Azure Container Registry and push local Docker images to it. It involves setting up the registry in Azure, preparing Docker images on the local host, and then pushing them to the cloud registry. This method is beneficial for managing and storing customized container images in a centralized, network-accessible location.

# Deploying a Script to an AWS Virtual Machine

<br>

## Introduction to Script Deployment in AWS

Deploying scripts during the creation of a virtual machine in AWS allows for automatic execution of tasks like updating packages or configuring settings.

<br>

### Starting with AWS Management Console

- **Access**: Log in to the AWS Management Console.
- **Navigation**: Use the search bar to find and select EC2 for managing virtual machines.

<br>

### Instance Deployment Considerations

- **Location Selection**: Choose the appropriate AWS region for deployment.
- **Instance Creation**: Click on the 'Launch instance' button to start the process.

<br>

### Configuring the Virtual Machine

- **Naming**: Assign a name to the instance, e.g., `Ubuntu3`.
- **OS Image Selection**: Choose an OS image, such as Ubuntu Server 22.04.
- **Instance Type**: Select an instance type based on required CPU power and memory.
- **Key Pair Authentication**: Choose a key pair for secure SSH access.
- **Network Settings**: Configure network settings like security groups and SSH access rules.
- **Storage Options**: Allocate and configure storage as needed.

<br>

### Specifying Script Execution

- **Advanced Details**: Navigate to 'Advanced details' to access the 'User data' field.
- **Script Input**: Directly input commands or upload a script file.
- **Example Commands**: Include commands like `sudo apt update`, `sudo apt install apache2`, and logging test messages.

<br>

### Launching the Instance

- **Execution**: Click 'Launch instance' to start the virtual machine with the included script.

<br>

### Post-Launch Verification

- **Accessing the Instance**: Use SSH to connect to the instance after launch.
- **Verifying Script Execution**:
  - Check services (e.g., `sudo service apache2 status`).
  - View system logs (e.g., `cat /var/log/syslog | grep AWS`).

<br>

### Editing User Data

- **Accessing User Data**: Through Instance settings, select 'Edit user data' to view the script.
- **Limitation**: Editing is not possible while the instance is running.

<br>

## Conclusion

Deploying scripts to AWS virtual machines during launch simplifies post-deployment tasks. Understanding how to input scripts into the AWS Management Console and verify their execution post-launch is crucial for effective cloud-based automation.

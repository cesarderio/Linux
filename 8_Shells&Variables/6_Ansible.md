# Installing and Configuring Ansible

<br>

## Introduction

Ansible is a powerful tool for centralized configuration management and automation, allowing you to manage numerous Linux hosts efficiently. This guide covers the basic installation and configuration of Ansible.

<br>

## What is Ansible?

1. **Centralized Management**:
   - Ansible is used for managing multiple Linux hosts from a central point.
   - Eliminates the need to manually configure each host, which is not scalable for large environments.

2. **Functionality**:
   - Performs configurations and command executions remotely over the network.

<br>

## Installing Ansible

1. **Adding Ansible Repository**:
   - Command: `sudo apt-add-repository ppa:ansible/ansible`
   - Adds a Personal Package Archive (PPA) for Ansible, which may not be included in standard repositories.

2. **Installing Ansible**:
   - Command: `sudo apt install ansible`
   - Installs Ansible from the added repository.

<br>

## Basic Configuration

1. **Navigating to Ansible Directory**:
   - Command: `cd /etc/ansible`
   - If the directory doesn't exist, create it.

2. **Configuring Hosts File**:
   - Edit the `hosts` file (e.g., `sudo nano hosts`).
   - Define host groups and specify managed hosts' IP addresses.
   - Example entry: `10.0.0.7 ansible_user=cblackwell ansible_ssh_pass=Pa$$w0rdABC123`

3. **Security Considerations**:
   - Storing SSH passwords in the hosts file can be a security risk.
   - Alternatives include using SSH keys for authentication.

4. **Setting Python Interpreter**:
   - Specify the Python interpreter version if needed in the `hosts` file.
   - Example: `ansible_python_interpreter=/usr/bin/python3`

<br>

## Testing Ansible Connectivity

1. **Ansible Ping Module**:
   - Command: `sudo ansible all -m ping`
   - Tests SSH connectivity to all hosts listed in the Ansible inventory.
   - Success is indicated by green text and a `SUCCESS` message.

<br>

## Running Linux Commands with Ansible

1. **Executing Commands**:
   - Command: `sudo ansible all -a "ls /"`
   - Runs a specified command on all managed nodes.

2. **Output Redirection**:
   - Redirect command output to a file for record-keeping.
   - Example: `sudo ansible all -a "ls /" > /home/cblackwell/rootlisting_ansiblenodes.txt`

<br>

## Using Ansible Playbooks

1. **Creating Playbooks**:
   - Use YAML syntax to write Ansible Playbooks.
   - Define tasks, such as package updates using the `apt` module.

2. **Executing Playbooks**:
   - Command: `sudo ansible-playbook [playbook-file]`
   - Executes the tasks defined in the playbook on all specified hosts.

<br>

## Conclusion

Ansible is a versatile tool for automating the configuration and management of Linux environments. By setting up Ansible correctly and understanding its basic usage, you can efficiently manage multiple systems, reducing the need for repetitive manual configurations. For larger deployments, similar tools like Puppet or Terraform can be considered.

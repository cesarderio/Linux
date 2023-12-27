# Setting Up SSH with Public Key Authentication in Linux

<br>

## Introduction

- **Objective**: Securely connect to a remote Linux server from a client machine using SSH with public key authentication.
- **Benefits**: Enhanced security through key-based authentication.

<br>

## Steps for Configuring SSH

<br>

### On the Client Machine

1. **Generate SSH Key Pair**:
   - Command: `ssh-keygen`
   - Process: Creates a unique key pair (public and private).
   - Location: Keys are stored in `/home/cblackwell/.ssh/`.
   - Security: Private key (`id_rsa`) is passphrase protected.

2. **Copy Public Key to Server**:
   - Command: `ssh-copy-id cblackwell@<server_IP_address>`
   - Purpose: Adds the public key (`id_rsa.pub`) to the server's `authorized_keys` file.
   - Authentication: Requires server password for initial setup.

<br>

### On the Server

1. **Verify Key Placement**:
   - Navigate to `.ssh` directory.
   - Command: `cat authorized_keys`
   - Confirmation: Ensures the client's public key is listed.

2. **Establish SSH Connection**:
   - From the client, initiate SSH: `ssh cblackwell@<server_IP_address>`
   - Authentication: Requires the passphrase for the private key.
   - Connection: Securely logged into the server without needing the server's password.

<br>

### Key Points

- **Private Key Security**: Private key remains on the client machine and is never transferred to the server.
- **Server Side**: Public key is added to the `authorized_keys` file in the server's `.ssh` directory.
- **Connection Process**: Once set up, SSH connections are authenticated using the key pair, bypassing the need for the server's password.

<br>

## Conclusion

- **Enhanced Security**: SSH with public key authentication provides a more secure connection method compared to password-based authentication.
- **Ease of Use**: After initial setup, connecting to the server is straightforward and more secure.
- **Wider Application**: This method can be replicated across multiple client-server setups for consistent security practices.

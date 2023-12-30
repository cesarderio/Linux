# Configuring SSH Remote Management

<br>

## Introduction

This guide demonstrates how to set up SSH remote management, a secure method of accessing Linux hosts remotely, replacing less secure protocols like telnet or rlogin.

<br>

### Steps for SSH Key Generation and Setup

1. **Generating SSH Keys**:
   - Use `ssh-keygen` to create a public and private RSA key pair.
   - Save the private key in the `.ssh` directory of the user's home folder (`id_rsa`).
   - Protect the private key with a passphrase.

2. **Transferring Public Key**:
   - The public key (`id_rsa.pub`) should be transferred to the server.
   - Use `ssh-copy-id user@server_ip` to automate this process.

3. **Verifying Key Transfer**:
   - On the server, the public key must be in the `.ssh/authorized_keys` file of the user's home directory.

<br>

### Example Scenario

- **Client Machine (Ubuntu2)**:
  - User `jgold` generates SSH keys and uses `ssh-copy-id` to transfer the public key to the server.

- **Server Machine (Ubuntu1)**:
  - Has a user `jgold` with a corresponding `.ssh/authorized_keys` file containing the transferred public key.

<br>

### Connecting to the Server

- **SSH Command**: `ssh jgold@server_ip`
- **Authentication**: The first connection will ask for the server's fingerprint verification and subsequently for the passphrase of the private key (not the server account's password).

<br>

## Conclusion

Setting up SSH remote management enhances security by adding an additional layer of authentication. It's crucial for Linux administrators to understand and implement this process for secure remote access to Linux hosts.

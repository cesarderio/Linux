# Transferring Files in Linux Using SCP and SFTP

<br>

## Introduction

Transferring files securely between Linux hosts can be achieved using SCP (Secure Copy Protocol) and SFTP (SSH File Transfer Protocol). Both methods rely on SSH for secure data transmission.

<br>

## SCP (Secure Copy Protocol)

<br>

### Using SCP on the Client Machine

1. **Basic File Transfer**:
   - Example Command: `scp cblackwell@<server_IP>:/home/cblackwell/projects/Project_A.txt .`
   - Copies `Project_A.txt` from the server to the current directory on the client.

2. **Transferring Multiple Files**:
   - Use `-r` for recursive copying.
   - Example Command: `scp -r cblackwell@<server_IP>:/home/cblackwell/projects ./projects`
   - Copies the entire `projects` directory from the server to a local directory named `projects`.

<br>

### Authentication

- SCP utilizes SSH public key authentication.
- For first-time use in a session, it requires the passphrase for the private key.

<br>

## SFTP (SSH File Transfer Protocol)

<br>

### Using SFTP for Interactive File Transfer

1. **Starting SFTP Session**:
   - Example Command: `sftp cblackwell@<server_IP>`
   - Enters an interactive SFTP session.

2. **Navigating Directories**:
   - `pwd` and `ls` for server-side directory and files.
   - `lpwd` and `lls` for client-side directory and files.

3. **Uploading Files to Server**:
   - `put <local_file>`
   - Example: `put sample_local_file.txt` uploads a file to the server's current directory.

4. **Downloading Files from Server**:
   - `get <remote_file>`
   - Example: `get filelist.txt` downloads a file from the server to the client's current directory.

5. **Exiting SFTP Session**:
   - Use `exit` to terminate the session.

<br>

## Key Points

- **SCP** is useful for straightforward file transfers, allowing for single or multiple file transfers with or without directory structure.
- **SFTP** provides an interactive interface, more suitable for managing files and directories, akin to an FTP session but secured via SSH.
- Both methods provide secure file transfer using SSH encryption and are widely used for transferring data between Linux hosts.

<br>

## Conclusion

SCP and SFTP are powerful tools in Linux for securely transferring files over a network. They leverage the security of SSH and offer flexibility in file transfer methods, catering to different user preferences and requirements.

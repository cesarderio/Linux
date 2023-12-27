# File Integrity and Authentication in Linux

<br>

## Introduction

In this session, we delve into the 'Integrity' aspect of the CIA security triad, focusing on how Linux systems can ensure data is trustworthy and has not been tampered with.

<br>

## File Hashing for Integrity

<br>

### Concept

- File hashing involves creating a unique hash value (or message digest) from a file’s contents using a one-way hashing algorithm.
- The integrity of a file is verified by comparing its current hash value with a previously generated hash.

<br>

### Process

1. **Generating a Hash**:
   - Use tools like `sha256sum` to generate a hash value for a file.
   - Command: `sha256sum hello.sh`
   - The output is a fixed-length hash, regardless of the data size.

2. **Detecting Changes**:
   - Modify the file and regenerate its hash.
   - Any alteration in the file will result in a different hash value.

<br>

### Legal and Forensic Use

- Digital forensic analysts use hashing to ensure the integrity of seized digital evidence.
- Hashing validates that the original data remains intact and unchanged.

<br>

### Algorithms

- Popular algorithms include SHA-256 and older ones like MD5 (though deprecated due to security vulnerabilities).

<br>

## Email Digital Signatures

<br>

### Purpose

- Email digital signatures authenticate the sender and ensure the message hasn’t been altered.
- The sender’s private key creates the signature, and the recipient uses the sender’s public key for verification.

<br>

### Security Consideration

- The security of a digital signature hinges on the sender's private key remaining confidential and protected.

<br>

## VPNs for Integrity and Authentication

- Corporate VPNs create encrypted and authenticated tunnels for secure data transmission.
- They are essential for linking branch offices and facilitating secure remote work.

<br>

## Blockchain and Cryptocurrency

- Blockchain technology employs hashing to validate transactions, ensuring integrity and authentication in cryptocurrency exchanges.

<br>

## Demonstrating File Hashing in Linux

1. **Creating Hashes**:
   - Use the `sha256sum` command for generating a hash.
   - Command: `sha256sum hello.sh`

2. **Modifying and Rehashing**:
   - Append data to the file and rehash to demonstrate the change.
   - Commands: `echo "new data" >> hello.sh` and `sha256sum hello.sh`

3. **Storing Hashes**:
   - Save hashes in a file using output redirection (`>` or `>>`).
   - Useful for web administrators to monitor file changes on a website.

<br>

## Conclusion

Integrity and authentication are crucial for ensuring data reliability in Linux systems. By employing file hashing and digital signatures, Linux administrators can detect unauthorized modifications and authenticate data sources. Hashing is especially significant in legal and forensic contexts, while also serving a vital role in maintaining the security of email communications and blockchain transactions. Understanding and correctly implementing these cryptographic techniques are essential for maintaining the integrity and authenticity of data in a Linux environment.

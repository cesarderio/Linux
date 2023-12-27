# Building Linux Software from Source

<br>

## Introduction

Building software from source is a valuable skill for Linux technicians. It involves compiling source code into executable binaries when the software isn't readily available via package managers like apt, yum, or pacman.

<br>

## Setting Up for Compilation

1. **Creating a Download Directory**:
   - Command: `mkdir downloads`
   - Prepares a designated directory for source code.

2. **Downloading Source Code**:
   - Example: Downloading Git's source code using `curl`.
   - Command: `curl --output [filename.tar.gz] [URL]`
   - Extracts the compressed file with `tar -zxf [filename.tar.gz]`.

<br>

## Preparing for Compilation

1. **Exploring the Source Directory**:
   - Command: `cd [source-directory]`
   - Reviews files, including `.c` files and a `configure` script.

2. **Running the Configure Script**:
   - Command: `./configure`
   - Checks for a suitable compiler and necessary dependencies.

<br>

## Installing Compiler and Dependencies

1. **Installing C Compiler**:
   - Command: `sudo apt install gcc`
   - Necessary to compile C language source code.

2. **Re-running Configure**:
   - Ensures the presence of a C compiler and required dependencies.

<br>

## Compiling the Software

1. **Using Make Command**:
   - Command: `sudo make`
   - Generates binary installation files from source code.

2. **Resolving Compilation Errors**:
   - Reference installation instructions for required packages.
   - Errors may occur without proper dependencies.

<br>

## Completing Installation

1. **Finalizing Installation**:
   - Command: `sudo make install`
   - Installs the compiled software onto the system.

2. **Verifying Installation**:
   - Command: `git --version`
   - Confirms the successful installation of the compiled software.

<br>

## Conclusion

Building software from source is a crucial aspect of Linux administration, especially when specific versions or customizations are needed that aren't available in standard repositories. This process requires careful attention to dependencies, compiler installation, and following appropriate documentation.

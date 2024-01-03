# Writing and Running a Simple Shell Script

<br>

## Introduction to Simple Shell Scripts

Simple shell scripts are great tools for automating repetitive tasks in Linux. They are essentially text files filled with executable commands, which can be manually run or scheduled via cron.

<br>

### Determining Script Functionality

- **Purpose of Script**: Decide what tasks you want the script to automate.
- **Script Requirements**: Determine the sequence of commands needed to accomplish these tasks.

<br>

### Choosing the Shell

- **Shebang Line**: The first line in the script, which specifies the shell to use, e.g., `#!/bin/bash`.
- **Shell Selection**: Choose the shell based on script requirements (Bash, C shell, Korn shell, etc.).

<br>

### Script Creation and Editing

- **File Extension**: Commonly `.sh` but not mandatory.
- **Text Editor**: Use text editors like nano to write the script, e.g., `nano script1.sh`.

<br>

### Script Content

- **Shebang Line**: The first line, e.g., `#!/bin/bash`, is critical for specifying the shell.
- **Command Execution**: Add Linux commands to the script file. These can be on separate lines or separated by `;` for compactness.
- **Example**: A script that calculates the total size of `.htm` files in a directory.

<br>

### Script Execution

- **Setting Permissions**: Use `chmod +rx scriptname.sh` to make the script readable and executable.
- **Running the Script**: Execute the script using `./scriptname.sh` in its directory.

<br>

## Conclusion

Writing and running simple shell scripts in Linux is a foundational skill for automating routine tasks. By understanding the basics of shell scripting, such as setting up the shebang line, scripting syntax, and execution permissions, you can efficiently create and run scripts to perform a variety of functions.

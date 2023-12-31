# Managing Linux Hosts with Shell Scripts

<br>

## Introduction to Linux Shell Scripts

Linux shell scripts are powerful tools for automation and simplification of repetitive tasks. They are text files containing executable commands and can be scheduled for execution using tools like cron.

<br>

### Basics of Shell Scripts

- **File Extension**: Commonly `.sh`, but not mandatory.
- **Shebang Line**: Specifies the shell type (e.g., `#!/bin/bash` for Bash shell).
- **Shell Variants**: Shell syntax varies (sh, Bash, C shell, Korn shell, etc.).

<br>

### Writing Shell Scripts

- **Commands**: Include any valid Linux command or reference other scripts.
- **Permissions**: Require execute (x) and read (r) permissions, settable via `chmod +rx scriptname.sh`.
- **Functions**: Define reusable code blocks within scripts. Example: `function show_ipinfo() { ... }`.

<br>

### Example: Displaying Function Output

- **Command**: `show_ipinfo` (function defined in the script).
- **Output**: Displays IP information and returns to the command prompt.

<br>

### Useful Commands in Scripts

- **grep**: Filters lines from files or output. Example: `grep -i "^toronto" /budgets/*.xls`.
- **egrep**: Extended grep with regex support. Example: `egrep "^Y{2,}" airports.txt`.
- **tee**: Writes output to both the file and screen. Example: `lsblk --scsi | tee filename`.
- **find**: Searches files with specific criteria. Example: `find / -name "*.xls" -user cblackwell > cblackwell_files.txt`.

<br>

### Special Redirections

- **Error Redirection**: `2>` redirects error output. Example: `find / -name "*.xls" 2> /dev/null`.

<br>

### Editing Content with sed and awk

- **sed**: Stream editor for search and replace. Example: `sed -e "s/toronto/vancouver/" file.txt`.
- **awk**: Processes text files and data extraction. Example: `awk 'NR>1' locations.txt` to skip the first line.

<br>

### Sample Basic Bash Shell Script

- **Shebang**: `#!/bin/bash`
- **Clear Screen**: `clear`
- **Echo Command**: `echo "Welcome to $(hostname), today is $(date)"`.

<br>

### Script Variables and Input

- **Reading Input**: `read firstname` captures user input into a variable.
- **Using Variables**: Refer to variables using `$`, like `$firstname`.

<br>

## Conclusion

Shell scripting in Linux is a versatile and essential skill for effective system management. It involves understanding different shell types, script permissions, and incorporating various Linux commands for task automation. By mastering shell scripts, you can significantly enhance the efficiency of managing Linux hosts.

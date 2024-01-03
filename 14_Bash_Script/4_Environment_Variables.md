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
- **Functions**: Define reusable code blocks within scripts, like `function backup() { ... }`.

<br>

### Linux Environment and Shell Script Variables

#### Environment Variables

- **Viewing**: Use `env` to display all environment variables.
- **Case Sensitivity**: Variables like `USER` and `PATH` are case-sensitive.
- **Accessing Values**: Use `echo $VARIABLE_NAME` to display a variable's value.

#### User-Defined Variables

- **Creating Variables**: For example, `city="Zurich"` creates a variable named `city`.
- **Scope**: Variables defined in the shell are session-specific.

#### Variable Expansion and Exporting

- **Command Substitution**: Use backticks (`` `command` ``) for dynamic values, e.g., `currentdate=$(date)`.
- **Exporting Variables**: Use `export variable_name` to make a variable available in sub-shells.

#### Exit Codes

- **Checking Exit Codes**: Use `echo $?` to view the exit code of the last executed command.
- **Interpretation**: A `0` exit code indicates success, while non-zero values (e.g., `127`) indicate an error.

<br>

### Special Function with Redirection

- **Function `backup`**:

  ```bash
  function backup {
      tar -cvf backup-$year-$month-$day.tar /path/to/directory >> /var/log/backup_log-$date_var.log
  }
  ```

- **Purpose**: Appends the output of the `tar` command to a log file.

<br>

## Conclusion

Shell scripting in Linux is a versatile and essential skill for effective system management. Understanding environment variables, variable expansion, and exit codes are critical aspects of advanced scripting. Mastery of these concepts enhances the effectiveness and reliability of managing Linux hosts.

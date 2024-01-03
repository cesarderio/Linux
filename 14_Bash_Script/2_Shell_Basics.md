# Shell Script Comparison

<br>

## Shell Script Comparison, Piping, and Redirection Operators

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

### Comparison Operators in Shell Scripts

#### The `if` Statement

- **Usage**: Tests a condition.
- **Example**:

  ```bash
  if test $USER = "root"; then
      echo "Welcome root!"
  else
      echo "Welcome $USER"
  fi
  ```

<br>

#### The `case` Construct

- **Usage**: For multiple possible values.
- **Example**:

  ```bash
  case $choice in
      1) exit;;
      2) ip a;;
      *) echo "I don't know";;
  esac
  ```

<br>

### Piping and Redirection in Shell Scripts

#### Piping Commands

- **Example**: Creating a variable `DGW_VAR` to store default gateway IP.

  ```bash
  DGW_VAR=$(ip route show | grep "default" | tr -s ' ' ':' | cut -d':' -f3)
  echo $DGW_VAR
  ```

<br>

#### Redirection

- **Input Redirection**: `<` for data from a file.
- **Output Redirection**: `>` for data to a file, `>>` for appending data.
- **Error Redirection**: `2>` for redirecting error output.

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

Shell scripting in Linux is a versatile and essential skill for effective system management. It involves understanding different shell types, script permissions, and incorporating various Linux commands for task automation. Mastering shell scripts enhances the efficiency of managing Linux hosts.

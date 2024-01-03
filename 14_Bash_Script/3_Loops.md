# Shell Script Looping Constructs 

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

### Looping Constructs in Shell Scripts

#### The `for` Loop

- **Usage**: Repeats statements with multiple iterations.
- **Example**:
  ```bash
  for i in /webfiles/*.htm; do
      currentsize=$(ls -l $i | tr -s ' ' | cut -d' ' -f5)
      let totalsize+=currentsize
  done
  echo "Total size: $totalsize" | tee results.txt
  ```

<br>

#### The `while` Loop

- **Usage**: Continues looping as long as a condition is true.
- **Example**:
  ```bash
  while true; do
      clear
      echo "UTILITY MENU"
      echo "1. Option"
      echo "2. Exit"
      read selection
      case $selection in
          1) show_ipinfo;;
          2) clear; exit;;
      esac
      read junk
  done
  ```

<br>

#### The `until` Loop

- **Usage**: Runs until a specified condition becomes true.
- **Example**:
  ```bash
  until [ condition ]; do
      # commands
  done
  ```

<br>

#### Using `break` and `continue`

- **`break`**: Exits the loop entirely.
- **`continue`**: Skips to the next iteration of the loop.
- **`select`**: Used for creating menu systems.

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

Shell scripting in Linux is a versatile and essential skill for effective system management. It involves understanding different shell types, script permissions, and various Linux commands, including looping constructs, for task automation. Mastering shell scripts enhances the efficiency of managing Linux hosts.

# Working with Environment Variables in Linux

<br>

## Introduction

Environment variables in Linux are an essential aspect of system configuration and scripting. They store values that can be used across the system and in shell scripts. Understanding how to manage and utilize environment variables is crucial for effective Linux administration.

<br>

## Understanding Environment Variables

1. **Definition**:
   - Environment variables are memory storage locations that retain user-defined values.
   - They can store various types of data like names, IDs, IP addresses, etc.

2. **Listing Variables**:
   - Command: `env`
   - This command lists all environment variables and their values in the current session.

3. **Case Sensitivity**:
   - Environment variable names are case-sensitive in Linux.

4. **PATH Variable**:
   - One of the most crucial environment variables, used to locate binaries.
   - View PATH: `echo $PATH`

<br>

## Creating and Using Variables

1. **Creating Variables**:
   - Syntax: `VariableName="Value"`
   - Example: `CostCenter="Toronto"`

2. **Displaying Variable Value**:
   - Use `echo` to display the value of a variable.
   - Example: `echo $CostCenter`

3. **Storing Command Output in Variables**:
   - Use backticks `` ` ` ` to assign the output of a command to a variable.
   - Example: `IP=`ip a | grep inet | grep brd``

<br>

## Variable Scope and Persistence

1. **Local vs. Global Scope**:
   - By default, variables are local to the current shell session.
   - Use `export` to make a variable available to child shell sessions.
   - Example: `export CostCenter`

2. **Visibility in Scripts**:
   - A script runs in a new shell; variables must be exported to be visible.
   - Example: A script echoing `$CostCenter` will only display the value if `CostCenter` is exported.

3. **Setting Persistent Variables**:
   - For persistence across sessions, define variables in startup files like `.bashrc` or `.profile`.

<br>

## Managing Environment Variables in Different Shells

1. **Shell Differences**:
   - The method of handling environment variables can vary between shells (Bash, Ksh, Csh).
   - The syntax and commands might differ slightly.

2. **Example with C Shell**:
   - Different prompt and behavior, like lack of tab completion for some commands.
   - Variables may need different syntax or commands to be set or exported.

<br>

## Practical Application

1. **Editing User Shell**:
   - The default shell for a user is defined in `/etc/passwd`.
   - Change a user's default shell by editing this file.
   - Example: Changing `mbishop`'s shell to `/usr/bin/csh`.

2. **Creating and Running Shell Scripts**:
   - Start scripts with a shebang (`#!`) followed by the shell path.
   - The shebang line determines the script's executing shell.
   - Example: `#!/bin/bash` for a script to run with Bash.

<br>

## Conclusion

Environment variables in Linux are powerful tools for customizing and controlling the user environment and scripting behavior. Understanding how to set, export, and use these variables across different shells and scripts is vital for efficient system management and automation in Linux.

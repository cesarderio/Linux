# Creating Shell Script Functions in Linux

<br>

## Introduction to Shell Script Functions

A function in a shell script is a collection of commands or expressions that you can execute by invoking the name of the function. While similar to a shell script, a function differs in that a shell script can contain numerous function definitions, which you can call as needed. Functions can also be defined directly at the command prompt.

<br>

### Creating a Basic Function

- **Using the `function` Keyword**: Create a function in the Bash shell with the `function` keyword.
- **Function Naming**: For example, name a function `general_details()`.

<br>

### Function Structure

- **Opening and Closing Braces**: Functions are defined within `{ }`.
- **Commands Within a Function**: Inside the braces, include the commands your function should execute. For example, `clear`, `hostname`, and `id` commands.

<br>

### Invoking Functions

- **Calling the Function**: Invoke a function by typing its name, e.g., `general_details`. Parentheses are not required when calling the function.

<br>

### Function Persistence

- **Session Persistence**: Functions exist only for the duration of the shell session unless saved in a startup file.

<br>

### Advanced Function Concepts

- **Arguments in Functions**: Functions can be designed to accept arguments, although the example function does not.
- **Script Libraries**: Functions can be centralized in script libraries, avoiding the need to copy the function definition into each shell script.

<br>

### Practical Example: `show_ipinfo` Function

- **Defining `show_ipinfo`**: This function is defined with commands to retrieve IP information.
- **Variable Assignments**: Variables like `IP_VAR` and `DGW_VAR` are used within the function to store command results.
- **Command Execution**: The function executes commands like `ifconfig` and `ip route show` to fetch network details.

<br>

### Script Execution and Permissions

- **Executing Scripts**: Use `chmod` to set the necessary permissions and then run the script using `./functiontest.sh`.
- **Exporting Functions**: Export a function with `export -f` to make it available outside its defining script or session.

<br>

## Conclusion

Creating and using functions in Linux shell scripts enhances script flexibility and reusability. Understanding function structure, invocation, and scope is crucial for effective scripting in Linux environments.

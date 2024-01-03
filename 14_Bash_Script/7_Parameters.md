# Parameterizing a Shell Script

<br>

## Introduction to Parameterizing Shell Scripts

Parameterizing a shell script involves writing the script to accept and use command line parameters, thereby altering its behavior based on input.

<br>

### Creating a Script with Parameters

- **Starting Point**: Use a text editor like nano to open and edit a script, e.g., `script2.sh`.
- **Shebang Line**: Ensure the script starts with `#!/bin/bash` for the Bash interpreter.

<br>

### Basic Parameter Usage in Script

- **Example Usage**: Echoing back script name and parameters.
  - `$0` is used to display the script name.
  - `$1`, `$2`, etc., represent the first, second, and subsequent parameters passed to the script.

<br>

### Testing the Script

- **Execution**: Use `./scriptname.sh` to run the script.
- **Passing Parameters**: Add parameters after the script name, e.g., `./script2.sh John Doe`.

<br>

### Advanced Parameter Handling

- **Using `getopts`**: For more complex parameter handling, like in `script3.sh`.
- **Defining Accepted Options**: Use `getopts` to specify which options the script should accept, e.g., `-h` and `-o`.

<br>

### Case Statement for Options

- **Option Handling**: Use a case statement to define actions based on specific options.
- **Capturing Option Values**: Use `$OPTARG` to get the value associated with an option.

<br>

### Error Handling in Script

- **Catch-all Case**: Handle unexpected or missing values with a default case in the script.
- **Example**: Display a message if required values for parameters are not supplied.

<br>

### Running Advanced Script

- **Testing Different Scenarios**: Try running the script with various combinations of options and values.
- **Observing Behavior**: Check how the script responds to different inputs.

<br>

## Conclusion

Parameterizing a shell script allows for more dynamic and flexible script execution. Understanding how to capture and use command line arguments enables the creation of more versatile and responsive scripts.

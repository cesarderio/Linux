# Working with While Loops in Linux

<br>

## Introduction to While Loops

This demonstration focuses on how to use a while loop in Linux, applicable both at the command line and within shell scripts.

<br>

### Basic While Loop Construction

- **Variable Initialization**: Start by creating a variable, such as `i`, and set its initial value (e.g., `i=1`).
- **Loop Condition**: Write the while loop with a condition, like `while [ $i -le 6 ]`.

<br>

### Loop's Execution Block

- **Do-Done Block**: The loop's commands are written between `do` and `done`.
- **Incrementing the Variable**: Increment the variable within the loop, e.g., `i=$(( $i + 1 ))`.

<br>

### Creating an Endless Loop

- **Endless Loop Syntax**: Use `while true` to create a loop that runs indefinitely.
- **Application Example**: Create a menu system with options and use `read` to capture user input.

<br>

### Practical Use of Endless While Loop

- **Utility Menu**: Implement a utility menu that executes functions or commands based on user input.
- **Exiting the Loop**: Use a condition within the loop (e.g., `if [ $hours -eq -1 ]`) to break out of it.

<br>

### Complex While Loop Example

- **Reading Multiple Inputs**: Use `read` to capture multiple inputs in a single line.
- **Conditional Break**: Incorporate an `if` statement to exit the loop based on a specific input (`-1` to quit).
- **Calculating and Displaying Output**: Perform calculations (e.g., pay calculation) within the loop and display the results.

<br>

## Conclusion

While loops in Linux offer a flexible way to perform repeated actions based on conditional logic. They can be used for simple tasks, such as incrementing values, or more complex applications, like interactive menus and dynamic calculations.

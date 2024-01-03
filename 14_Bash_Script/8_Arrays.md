# Working with Array Variables in Linux

<br>

## Introduction to Array Variables

Array variables in Linux shell scripts allow for the storage and manipulation of a collection of similar data types.

<br>

### Creating Array Variables

- **Defining Arrays**: Define array variables at the command line, e.g., `colors[0]="red"`.
- **Element Indexing**: Array indices start at 0.

<br>

### Accessing Array Elements

- **Echo Command**: Use `echo ${array[index]}` to display specific array elements.
- **Example**: `echo ${colors[0]}` returns `red`, `echo ${colors[1]}` returns `blue`.

<br>

### Displaying Entire Arrays

- **Command**: `echo ${array[@]}` displays all elements of an array.
- **Counting Elements**: Use `echo ${#array[@]}` to display the number of elements.

<br>

### Character Count in Elements

- **Specific Element**: `echo ${#array[1]}` returns the character count of the second element.

<br>

### Modifying Array Elements

- **Direct Assignment**: Modify individual elements, e.g., `colors[1]="green"`.
- **Temporary Replacement**: `echo ${colors[@]/blue/green}` shows `red green` but doesn't change the array.

<br>

### Populating Arrays from Files

- **Example**: Load file contents into an array, e.g., `stockvaluesvar=( $(cat stockvalues.txt) )`.

<br>

### Iterating Over Arrays

- **For Loop**: Use a loop to iterate through array elements.
- **Example Loop**:

  ```bash
  for individualstockvalue in "${stockvaluesvar[@]}"
  do
      echo $individualstockvalue
  done
  ```

  This loop echoes each value in the `stockvaluesvar` array.

<br>

## Conclusion

Understanding and utilizing array variables in Linux enhances the ability to handle collections of data within shell scripts. Through commands and scripting techniques, arrays provide efficient ways to store, access, and manipulate multiple data elements.

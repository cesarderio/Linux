# Linux File System Hard and Soft (Symbolic) Links

<br/>

## Understanding Inodes

- **What is an Inode?**
  - It's a 128-byte entry in the filesystem table that describes a file or directory.
  - Contains metadata, including pointers to actual disk data blocks, owning user and group, permissions, and timestamps.

- **Checking Inode Numbers**
  - Use `ls -i` to display filesystem entries with their inode numbers.

<br/>

## Hard Links

- **Concept**
  - A hard link creates a new filename that points to an existing inode.
  - Allows multiple filenames to share a single inode, referencing the same file data on disk.

- **Characteristics**
  - File data is shared; modifying one link reflects in all.
  - Deleting a file only affects the data when the last hard link is removed.
  - Limited to a single disk partition.

- **Creating a Hard Link**
  - Use the `ln` command.
  - Example: `ln /budgets/file1.xls /home/cblackwell/file1.xls`
  - Creates a new entry in a different directory, but both point to the same inode.

- **Identifying Hard Links**
  - `ls -li` shows files with their inode numbers.
  - `ls -l` shows the count of hard links to a file.

<br/>

## Symbolic (Soft) Links

- **Concept**
  - A symbolic link (symlink) creates a new filename with a new inode that points to an existing filename.
  - Acts as a pointer or shortcut to another file.

- **Characteristics**
  - Has its own inode and metadata but points to another file's data.
  - Can span across disk partitions.
  - Modifications to file data are reflected across all symlinks.

- **Creating a Symbolic Link**
  - Use the `ln -s` command.
  - Example: `ln -s /budgets/file1.xls /home/cblackwell/file1.xls`
  - This creates a symlink in the user's home directory pointing to the original file.

- **Symlink Metadata**
  - Can have different owners, permissions compared to the original file.

<br/>

## Summary

- **Hard Links**
  - Multiple entries, one inode, same disk partition.
  - Ideal for creating alternate paths to a file within the same filesystem.

- **Symbolic Links**
  - Separate inodes, can point across partitions.
  - Useful for creating shortcuts or links to files located in different filesystems.


<br/>
<br/>

## Working With Hard and Soft (Symbolic) Links in Linux

<br/>

### Understanding and Creating Hard Links

- **Concept of Hard Links**
  - Hard links provide an alternative way to access the same file data.
  - They point to the same inode, sharing the same file data and metadata.

- **Creating a Hard Link**
  - Use the `ln` command without any flags.
  - Example: `ln customers.txt hardlink_customers.txt`
  - This creates a new file entry (`hardlink_customers.txt`) pointing to the same inode as `customers.txt`.

- **Observing Hard Link Behavior**
  - Both the original file and the hard link reflect the same content changes.
  - Use `ls -li` to view inode numbers. Hard links share the same inode number.

- **Limitation**
  - Hard links cannot span across different disk partitions.

<br/>

### Understanding and Creating Symbolic (Soft) Links

- **Concept of Symbolic Links**
  - Symbolic links, or symlinks, create a new file entry with a new inode that points to an existing filename.
  - They can have different permission sets, owners, and groups from the original file.

- **Creating a Symbolic Link**
  - Use the `ln -s` command.
  - Example: `ln -s customers.txt softlink_customers.txt`
  - Creates a symlink (`softlink_customers.txt`) pointing to `customers.txt`.

- **Observing Symbolic Link Behavior**
  - Symlinks have different inode numbers from the original file.
  - Modifications to file data are reflected in both the symlink and the original file.
  - Use `ls -li` to observe the different inode numbers.

- **Advantages**
  - Symlinks can span different file systems and disk partitions.

<br/>

### Practical Demonstration

- **Modifying File Content via Links**
  - Changes made to the file content through either the hard link or the symlink are reflected in all linked files.
  - Example: Modifying `customers.txt` through `softlink_customers.txt` updates the content in both files.

- **Visual Indicators**
  - In many Linux distributions, symlinks are visually differentiated (e.g., different text color, arrow symbol).

<br/>

### Summary

- **Hard Links**
  - Multiple file entries with the same inode.
  - Ideal for alternative file access within the same filesystem.

- **Symbolic Links**
  - Separate inode, points to an original file.
  - Flexible, can point to files across different filesystems and partitions.

[⏪ Return to index ⏪](./README.md)

## Working with Files

1. <details>
    <Summary><strong>What are the main basic commands for file handling in Linux terminal?</strong></Summary>

    ###
    - `touch` for creating files
    - `mv` for moving files
    - `cp` for copying files
    - `rm` for removing files
    - `ls` for listing files and directories.
</details>

2. <details>
    <Summary><strong>What are soft and hard links?</strong></Summary>

    ###
    - A hard link is a mirror reflection of the original file, sharing the same file data but displaying a different name and inode number.
    - A soft link, also known as a symbolic link, is more like a shortcut to the original file.
    - If the source file is deleted, moved or renamed the hard link still retains the file data but the soft will not work until the original file is restored.
</details>

3. <details>
    <Summary><strong>How do we create soft and hard links?</strong></Summary>

    ###
    ```
    # Create a hard link
    ln source_file.txt hard_link.txt

    # Create a soft link
    ln -s source_file.txt soft_link.txt
    ```
</details>

4. <details>
    <Summary><strong>How do we copy files in Linux?</strong></Summary>

    ###
    ```
    cp /path/to/original/file /path/to/copied/file
    ```
</details>

5. <details>
    <Summary><strong>How do we move or rename files in Linux?</strong></Summary>

    ###
    ```
    mv /path/to/original/file /path/to/new/file

    # We can use the dot to say the current directory.
    # We move source.txt to the current dir.

    mv test/source.txt .
    ```
</details>

6. <details>
    <Summary><strong>How do we archive in Linux?</strong></Summary>

    ###
    - The tar command, originally for tape archiving, is a versatile tool that can manage and organize files into one archive.
    - Meanwhile, gzip and bzip2 are used for file compression, reducing the file size and making data transmission easier.
    ###
    ```
    # To create a tar archive:
    tar cvf archive_name.tar directory_to_archive/

    # To extract a tar archive:
    tar xvf archive_name.tar

    # To create a gzip compressed tar archive:
    tar cvzf archive_name.tar.gz directory_to_archive/

    #To create a bzip2 compressed tar archive:
    tar cvjf archive_name.tar.bz2 directory_to_archive/
    ```
</details>

7. <details>
    <Summary><strong>What are the type of users in Linux?</strong></Summary>

    ###
    - Owners
    - Groups
    - Others
</details>

8. <details>
    <Summary><strong>Explain the following output: -rwxr--r--</strong></Summary>

    ###
    - First character `-`: Indicates if it is a regular file (`-`) or directory (`d`). 
    - `rwr`: The owner can read (`r`), write (`w`) and execute (`x`) the file.
    - `r--`: Groups can read only
    - `r--`: Others can read only

    > To check this output use `ls -l`
</details>

9. <details>
    <Summary><strong>How can you change permissions in Linux files?</strong></Summary>

    ###
    - The permissions can be changed using the `chmod`, `chown`, and `chgrp` commands.
</details>

10. <details>
    <Summary><strong>Which file would be accessed by which user is decided by two factors in Linux:</strong></Summary>

    ###
    - File ownership
    - File permission
</details>

11. <details>
    <Summary><strong>What is the differences with file and directory permissions?</strong></Summary>

    ###
    - Permissions for files
        - Read: Can view or copy file contents
        - Write: Can modify file content
        - Execute: Can run the file (if its executable)

    - Permissions for directories
        - Read: Can list all files and copy the files from directory
        - Write: Can add or delete files into directory (needs execute permission as well)
        - Execute: Can enter the directory
</details>

12. <details>
    <Summary><strong>Explain the following output: </strong><code>-rwxrw-r-- 1 abhi itsfoss 457 Aug 10 11:55 agatha.txt</code></Summary>

    ###
    - `-`: File type
    - `rwxrw-r--`: Permissions
    - `1`: Hard Link Count (1 by default)
    - `abhi`: User Owner
    - `itsfoss`: Group Owner
    - `457`: File Size (in bytes)
    - `Aug 10 11:15`: Modification Timestamp
    - `agatha.txt`: File name

    > To check this output use `ls -l`
</details>

13. <details>
    <Summary><strong>What are the two ways to use the chmod (change mode) command?</strong></Summary>

    ###
    - Absolute mode
        - Example: `chmod 764 agatha.txt`
    - Symbolic mode
        - Example: `chmod g+x agatha.txt`
</details>

14. <details>
    <Summary><strong>How do we use the absolute mode of chmod?</strong></Summary>

    ###
    - Permissions are represented in numeric form (octal system to be precise).
        - r (read) = 4
        - w (write) = 2
        - x (execute) = 1
        - – (no permission) = 0
    ###
    | Number         | Permission |
    | -------------- | ---------- |
    | 0              | -          |
    | 1              | -x         |
    | 2              | -w-        |
    | 3 (i.e. 2+1)   | -wx        |
    | 4              | r--        |
    | 5 (i.e. 4+1)   | r-x        |
    | 6 (i.e. 4+2)   | rw-        |
    | 7 (i.e. 4+2+1) | rwx        |
</details>

15. <details>
    <Summary><strong>How do we use the symbolic mode of chmod?</strong></Summary>

    ###
    - Owners are denoted with the following symbols:
        - u = user owner
        - g = group owner
        - o = other
        - a = all (user + group + other)
    - Use mathematical operators to perform the permission changes:
        - + for adding permissions
        - – for removing permissions
        - = for overriding existing permissions with new value
    - Example: `chmod g+x agatha.txt` or `chmod a-x agatha.txt`
</details>

16. <details>
    <Summary><strong>How do we change file ownership in Linux?</strong></Summary>

    ### Chown (change owner)
    - To change the user owner of a file: `chown <new_user_name> <filename>`
    - To change the group: `chown :<new_user_group> <filename>`
    - To change user and group: `chown <new_user_name>:<new_user_group> <filename>`
    ### Chgrp (change group)
    - To change the group: `chgrp <new_user_group> <filename>`
</details>

17. <details>
    <Summary><strong>Why Abhi can't read the file if he is in the group itsfoss with read permissions? </strong><code>----r--rw- 1 abhi itsfoss 457 Aug 10 11:55 agatha.txt</code></Summary>

    ###
    - Because in Linux it first check for the user, next for the group and then for others, so in this case is taking owner permission.
    - He can read the file if someone change the owner, so he can perform group permissions.
</details>

18. <details>
    <Summary><strong>What are the common permission with the absolute mode of chmod?</strong></Summary>

    ###
    - 644: File Baseline
    - 755: Directory Baseline
    - 400: Key Pair
</details>
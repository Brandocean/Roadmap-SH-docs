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
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

8. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

9. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

10. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

11. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

12. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

13. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

14. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

15. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

16. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

17. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

18. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

19. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

20. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>
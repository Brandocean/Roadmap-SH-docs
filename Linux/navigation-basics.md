[⏪ Return to index ⏪](./README.md)

## Navigation basics

1. <details>
    <Summary><strong>What command do we use to change directories?</strong></Summary>

    ###
    ```console
    cd /path/to/directory
    ```
</details>

2. <details>
    <Summary><strong>What command do we use to list the contents of a directory?</strong></Summary>

    ###
    ```console 
    ls
    ```
</details>

3. <details>
    <Summary><strong>What command do we use to view current working directory?</strong></Summary>

    ###
    ```console 
    pwd
    ```
</details>

4. <details>
    <Summary><strong>What command do we use to display the mannual page for a command?</strong></Summary>

    ###
    ```console 
    man ls
    ```
</details>

5. <details>
    <Summary><strong>What command do we use to move files in Linux?</strong></Summary>

    ###
    ```console 
    mv [options] source destination
    ```
    - **source**: Is the directory you want to move
    - **destination**: Is where you want to move your source file
    - You can use this command without the [options] part

    ###
    > 💡 You can use it also to rename files for example `mv file.txt file2.txt` this gonna change the name of file.txt.
</details>

6. <details>
    <Summary><strong>How do we create files in Linux?</strong></Summary>

    ###
    ```console 
    # This command creates new file only

    touch newfile.txt
    ```

    ```console 
    # This command creates the file but first you need to write its content and escape with Ctrl + C

    cat > newfile.txt
    ```

    ```console 
    # This command creates the file and it need a string argument to redirect the output to the new file3.txt

    echo "This is the file name: file3" > file3.txt
    ```

    > 💡 The command echo itself only shows the string on console `echo "This is a file"`
</details>

7. <details>
    <Summary><strong>How do we delete files in Linux?</strong></Summary>

    ###
    ```console 
    # This command deletes the file named example.txt

    rm example.txt
    ```

    ```console 
    # This command deletes and ask for confirmation

    rm -i [filename]
    ```

    ```console 
    # This command removes an empty directory
    
    rmdir [directory] 
    ```
</details>

8. <details>
    <Summary><strong>What is the Linux system's directory structure?</strong></Summary>
    
    ###
    - Also known as the Filesystem Hierarchy Standard (FHS), is a defined tree structure that helps to prevent files from being scattered all over the system and organize them in a logical and easy-to-navigate manner.
</details>

9. <details>
    <Summary><strong>What is the structure of the Filesystem Hierarchy Standard (FHS)?</strong></Summary>

    ###
    - **/:** Root directory, the top level of the file system.
    - **/home:** User home directories.
    - **/bin:** Essential binary executables.
    - **/sbin:** System administration binaries.
    - **/etc:** Configuration files.
    - **/var:** Variable data (logs, spool files).
    - **/usr:** User programs and data.
    - **/lib:** Shared libraries.
    - **/tmp:** Temporary files.

    ###
    > [Overview of File System Hierarchy Standard](https://docs.redhat.com/en/documentation/red_hat_enterprise_linux/4/html/reference_guide/s1-filesystem-fhs#s3-filesystem-var)
</details>

10. <details>
    <Summary><strong>What is Linux?</strong></Summary>

    ###
    - Linux is an open-source operating system kernel that serves as the foundation for a wide range of operating systems.
</details>

11. <details>
    <Summary><strong>Who created Linux?</strong></Summary>

    ###
    - It was developed by Linus Torvalds in 1991.
</details>

12. <details>
    <Summary><strong>What are the main characteristics of Linux?</strong></Summary>

    ###
    - Open-source
    - Reliable
    - Multitasking and multiuser
    - Security
    - Portability
    - Its Command-Line Interface (CLI)
</details>

13. <details>
    <Summary><strong>What are the main functions of the Kernel?</strong></Summary>

    ###
    - **Process management:** it initiates, schedules, and terminates processes.
    - **Memory management:** it allocates and deallocates memory space for processes as well as implementing virtual memory.
    - Facilitates communication between hardware components and the OS.
    - Manages file permission and access control.
</details>

14. <details>
    <Summary><strong>What are the main Linux distributions?</strong></Summary>

    ###
    - **Ubuntu:** It's an excellent choice for beginners because of its user-friendly interface.
    - **Fedora:** The best fit for those people who are looking for the latest features and are security-conscious users
    - **Debian:** Best for servers and critical systems. Its package management system simplifies the software installation process.
    - **Arch Linux:** Known for its customization that allows the users to build their way up. Provides continuous updates with no need to reinstall apps again.

    ###
    ![Linux distributions](https://media.licdn.com/dms/image/D4D12AQG2sEF6uE_3aA/article-inline_image-shrink_1500_2232/0/1707854756486?e=1728518400&v=beta&t=cMVXHyMAanwymZZRxVeAyVdvHKpTcHFgEr8VVeXARug)
</details>

15. <details>
    <Summary><strong>What is a Linux distribution?</strong></Summary>

    ###
    - It is a complete set of packages that provide the users with a ready-to-use operating system (kernel, libraries, etc.)
</details>

16. <details>
    <Summary><strong>The bash shell is the default shell for most Linux distributions?</strong></Summary>

    ###
    - True
    - Because of its powerful scripting capabilities, extensive features, and compatibility with the Bourne shell (sh).
</details>

17. <details>
    <Summary><strong>How does we find files in our Linux system?</strong></Summary>

    ###
    ```
    # To find a directory and everything inside 
    find DIRECTORY_NAME

    # To find a specific file
    find -name FILE_NAME

    # To find files with a specific extension
    # Here we use a wildcard *
    find -name *.txt
    ```
</details>

18. <details>
    <Summary><strong>Explain the operator (&) and (&&)</strong></Summary>

    ###
    - `&`: Is used to run a command in the background, allowing you to continue using the terminal while the command is still executing. 
        - Example `sleep 10 &`
    - `&&`: we use it to run many commands at the same time but the command2 only gonna run if command 1 is successful. 
        - Example: `sudo apt update && sudo apt upgrade`
</details>

19. <details>
    <Summary><strong>Explain the operator (>) and (>>)</strong></Summary>

    ###
    - `>`: This operator allow us to take the output from a command we run and send that output to somewhere else.
        - Like the `echo` command that we use to create a file
    - `>>`: Is the same as `>` but with this command we redirect our output at the end of the file
        - If we use only `>` it will overwrite our file   
</details>
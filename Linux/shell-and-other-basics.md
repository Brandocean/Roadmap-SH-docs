[⏪ Return to index ⏪](./README.md)

## Shell and Other Basics

1. <details>
    <Summary><strong>What is the Linux Shell?</strong></Summary>

    ###
    - The Linux shell is a command-line interface or terminal used to interact directly with the operating system. 
    - The shell helps facilitate system commands and acts as an intermediary interface between the user and the system’s kernel.
</details>

2. <details>
    <Summary><strong>What are the types of shells in Linux?</strong></Summary>

    ###
    - Bourne Shell (sh)
    - C Shell (csh)
    - Bourne-Again Shell (bash).
</details>

3. <details>
    <Summary><strong>What is the command path?</strong></Summary>

    ###
    - The PATH is an environment variable in Linux that contains a list of directories.
    - Each directory in this list is separated by a colon (:).
    - Without a proper PATH, you'd need to type the full path to executables every time you want to run a command (e.g., /usr/bin/ls instead of just ls).
</details>

4. <details>
    <Summary><strong>How do we add new directories to the PATH variable?</strong></Summary>

    ###
    - Type in the terminal `PATH=$PATH:NEW_DIRECTORY`. This copy all the PATH and add the new directory
    - Example: `PATH=$PATH:~/bin`. This add a directory `bin` that is in the home directory.
    - You can add more directories if needed using the `:` to separate each one.
    ###
    > If you want a permanent change of the PATH variable you need to edit the .bashrc at the end with the following (this is an example with the ~/bin directory): 
    ```
    if [ -d ~/bin ]
    then
        PATH=$PATH:~/bin
    fi
    ```
    - This code checks if the directory exist add it to the PATH variable, else do nothing.
</details>

5. <details>
    <Summary><strong>What are the environment variables?</strong></Summary>

    ###
    - Environment variables are dynamic named values that can affect the behavior of running processes in a shell. 
    - They exist in every shell session.
    ### 
    ```
    # List all environment variables
    $ env

    # Print a particular variable like PATH
    $ echo $PATH
    ```
</details>

6. <details>
    <Summary><strong>How to Set Environment Variables in Linux?</strong></Summary>

    ###
    - `export VARIABLE_NAME=value`
    - Example: `export JAVA_HOME=/usr/bin/java`
</details>

7. <details>
    <Summary><strong>How to Make Environment Variables Persistent in Linux?</strong></Summary>

    ###
    - Edit the file `.bashrc` that is located in the user's home directory.
    - Add the definition of the environment variable at the end of the .bashrc file.
    ![Example-of-bashrc-variable](https://www.freecodecamp.org/news/content/images/2022/10/image-194.png)
    - For the changes to take effect, update the .bashrc file using `source .bashrc`
</details>

8. <details>
    <Summary><strong>What are the main commands for help?</strong></Summary>

    ###
    - To view the manual entry for any command, use: `man [command]`
        - It has an extensive documentation.
    - For built-in shell functions, use: `help [command]`
        - It has a brief documentation.
</details>

9. <details>
    <Summary><strong>How many streams opened has each process in Linux?</strong></Summary>

    ###
    - Every process typically has 3 streams opened.
</details>

10. <details>
    <Summary><strong>Which are the the 3 streams that are open in a process?</strong></Summary>

    ###
    - Standard Input (stdin): This is where the process reads its input from. 
        - The default is the keyboard.
    - Standard Output (stdout): The process writes its output to stdout. 
        - By default, this means the terminal.
    - Standard Error (stderr) - The process writes error messages to stderr. 
        - This also goes to the terminal by default.
</details>

11. <details>
    <Summary><strong>What are Redirects In Shell?</strong></Summary>

    ###
    - Redirection is a feature in Linux such that when executing a command, you can change the standard input/output devices.
</details>

12. <details>
    <Summary><strong>What are the most common Redirections?</strong></Summary>

    ###
    - `>`: Redirects standard output to a file but it overwrites.
        - Example: `ls -al > file_list.txt`.
    - `>>`: Redirects standard output to a file and appends to any existing content.
        - Example: `ls >> file_list.txt` here is not overwriting.
    - `<`: Redirects input from a file to a command.
        - Example: `tr 'o' 'b' file`, the file has `foo` inside so here the display will be `fbb` instead of foo because we use file as an input.
</details>

13. <details>
    <Summary><strong>What is the super user in Linux?</strong></Summary>

    ###
    - The Super User, also known as “root user”, represents a user account in Linux with extensive powers, privileges, and capabilities.
</details>

14. <details>
    <Summary><strong>How do we use the super user in Linux?</strong></Summary>

    ###
    - `su -` or `sudo su -`: Switches the current user to the root (In some cases you have the password or not depending on the distribution).
    - `sudo <command>`: To perform a command as superuser (if allowed in sudoers list)
</details>
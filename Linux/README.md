# Linux Roadmap
> Link to [Linux roadmap.sh](https://roadmap.sh/linux)

<details>
<Summary><strong>Articles / Files</strong></Summary>

###
- [Linux Journey](https://linuxjourney.com/)
- [Vim-repository](https://github.com/iggredible/Learn-Vim?tab=readme-ov-file)
- [Vim-game](https://vim-adventures.com/)

</details>

<details>
<Summary><strong>Common nano flags</strong></Summary>

###
| Flag | Description | Example |
| ---- | ----------- | ------- |
| `-I` | Enables automatic indentation.| `nano -I myfile.txt` |
| `-N` | No conversion from DOS/Mac format. | `nano -N myfile.txt` |
| `-T` | Sets the size of a tab to the given number of spaces. | `nano -T 4 myfile.txt` |
| `-U` | Enables undo functionality. | `nano -U myfile.txt` |
| `-Y` | Syntax highlighting. | `nano -Y sh myfile.sh` |
| `-c` | Constantly show the cursor position. | `nano -c myfile.txt` |
| `-i` | Automatically indents new lines. | `nano -i myfile.txt` |
| `-k` | Toggle cut so it cuts from cursor position. | `nano -k myfile.txt` |
| `-m` | Enable mouse support. | `nano -m myfile.txt` |
</details>

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

## Editing Files

20. <details>
    <Summary><strong>How do we edit files on Linux?</strong></Summary>

    ###
    ```
    nano [filename]
    ```
    ```
    vi [filename] or vim [filename]
    ```
    ```
    gedit [filename]
    ```
</details>

21. <details>
    <Summary><strong>What are the differences between nano and vi/vim?</strong></Summary>

    ###
    - `nano` is a basic text editor, which is easy to use and perfect for simple text file editing. 
    - `Vi/vim`, on the other hand, is more advanced and offers a wide range of features and commands.
</details>

22. <details>
    <Summary><strong>How do you save files with nano?</strong></Summary>

    ###
    - `Ctrl + O`.
</details>

23. <details>
    <Summary><strong>How do you exit nano?</strong></Summary>

    ###
    - `Ctrl + X`.
</details>

24. <details>
    <Summary><strong>What are the common issues with nano?</strong></Summary>

    ###
    - Nano not installed. 
        - Solution: Install nano
    - Unable to write the buffer `Error writing file_name: Permission denied`.
        - Solution: Change the file permissions
    - Nano opening in a new window. 
        - If you’re using a graphical interface, nano might open in a new window
        - Solution: If you want to open nano in the terminal, you can use the ‘-t’ option `nano -t myfile.txt`.
</details>

25. <details>
    <Summary><strong>How do we move between buffers with nano?</strong></Summary>

    ###
    - `Atl + >` or `Alt + <`.
</details>

26. <details>
    <Summary><strong>How do we copy and paste sections in our nano file?</strong></Summary>

    ###
    - To select your text use `Alt + A`
    - To copy select your text and use `Alt + ^`.
    - To paste just type `Ctrl + U`.
    - To cut select your text and use `Ctrl + K` 
</details>

27. <details>
    <Summary><strong>How do we move to the top and bottom of a file with nano?</strong></Summary>

    ###
    - `Alt + \` to go to the top.
    - `Alt + /` to go to the bottom.
</details>

28. <details>
    <Summary><strong>How do we search and replace words with nano?</strong></Summary>

    ###
    - To search type `Ctrl + W`, type the word you want to search and press Enter.
        - Do this many times to go through all the findings. 
    - To replace type `Alt + R`, type the word and the new-word and type enter
        - Type `yes` or `no` to check each finding or `A` to change all the findings.
</details>

29. <details>
    <Summary><strong>What are the three modes of Vim?</strong></Summary>

    ###
    - Normal: for navigation and manipulation.
    - Insert: for editing text.
    - Command: for executing commands.
</details>

30. <details>
    <Summary><strong>How do we write content with Vim?</strong></Summary>

    ###
    - Type `i` to get into INSERT mode.
</details>

31. <details>
    <Summary><strong>How do we save and quit a file with Vim?</strong></Summary>

    ###
    - `:wq` where `:w` is for save and `:q` is for quit.
    - Also you can use `ZZ`.
    - `:w FILE_NAME` if you want to create a new file with the actual information.
</details>

32. <details>
    <Summary><strong>How do we copy and paste with Vim?</strong></Summary>

    ###
    - Type `v` to enter the visual mode, select the section .you want to copy and press `y` to copy or `d` to cut. Finally type `P` to paste.
    - Type `yiw` to copy the current word.
    - Type `yy` to copy the current line or `dd` to delete it and copy.
</details>

33. <details>
    <Summary><strong>How do we repeat commands with Vim?</strong></Summary>

    ###
    - `.` (dot): will repeat the last command.
    - `N<command>`: will repeat the command N times.
        - Example: `2dd` will delete 2 lines.
</details>

34. <details>
    <Summary><strong>How do we move efficiently with Vim?</strong></Summary>

    ###
    - `NG`: Go to line N.
    - `gg`: shortcut for `1G` - go to the start of the file.
    - `G`: Go to last line
    - Word moves:
        - `w`: go to the start of the following word
        - `e`: go to the end of this word.
        - `W`: same as `w` but here a WORD is separated by blank characters.
        - `E`: same as `e` but here a WORD is separated by blank characters.

       ![Example-of-word](https://yannesposito.com/Scratch/img/blog/Learn-Vim-Progressively/word_moves.jpg) 
    - `%`: Go to the corresponding `(`, `{`, `[`.
</details>

35. <details>
    <Summary><strong>How do you can see your distribution in Linux?</strong></Summary>

    ###
    ```
    /etc/os-release
    ```
</details>

36. <details>
    <Summary><strong>How do you move with Vim?</strong></Summary>

    ###
    - `h`: left
    - `j`: down (it seems like a ⬇)
    - `k`: up
    - `l`: right
</details>

37. <details>
    <Summary><strong>How do we add content that is in another file with Vim?</strong></Summary>

    ###
    - In the Normal mode type: `r FILE_NAME`
</details>

38. <details>
    <Summary><strong>How can we run linux command with Vim?</strong></Summary>

    ###
    - In command mode type: `! LINUX_COMMAND`
    - Example: `! ls`
</details>

39. <details>
    <Summary><strong>What is a buffer?</strong></Summary>

    ###
    - A buffer is a chunk of memory that holds the text of a file that you're currently editing.
    - Example: When you open a new vim file you are in a new buffer.
</details>

40. <details>
    <Summary><strong>How move between buffers?</strong></Summary>

    ###
    - `bp`: to move to the previous buffer (buffer previous)
    - `bn`: to move to the next buffer (buffer next)
    - `bd`: if you want to delete the actual buffer
    - `badd`: if you want to add a buffer without switch (remains in the actual buffer).
</details>

41. <details>
    <Summary><strong>How do you we create a new buffer with Vim?</strong></Summary>

    ###
    - `:enew`: to create an empty buffer
</details>

42. <details>
    <Summary><strong>How do we find and replace with Vim?</strong></Summary>

    ###
    - `%s/OLD_WORD/NEW_WORD/g`:
    - If you only want to find type until OLD_WORD 
</details>

43. <details>
    <Summary><strong>How do we split with Vim?</strong></Summary>

    ###
    - `:split FILE_NAME` or `:sp FILE_NAME`: for horizontal split (or open two files in the same terminal window).
        - `vim -o FILE1 FILE2`: to open the files with this config.
    - `:vsplit FILE_NAME` or `:vsp FILE_NAME`: for vertical split (recommended).
        - `vim -O FILE1 FILE2`: to open the files with this config.
    - `Ctrl + ww`: to move between files.
    - `:q` to exit one buffer.
</details>

44. <details>
    <Summary><strong>How do we active line numbers in Vim?</strong></Summary>

    ###
    `:set number`: to active line numbers
    `:set nonumber`: to deactivate line numbers
</details>

45. <details>
    <Summary><strong>How do we configure Vim?</strong></Summary>

    ###
    - Open the file `.vimrc` in your home directory (/home/brandocean for example) and write the configuration that you want.
        - If you don't open the file in your home directory, changes would not be made.
    - Example: `set number` to have the line numbers each time we open a vim file.
</details>

46. <details>
    <Summary><strong>How do  Vim?</strong></Summary>

    ###
    - `h`: left
</details>

47. <details>
    <Summary><strong>How do you move with Vim?</strong></Summary>

    ###
    - `h`: left
</details>

48. <details>
    <Summary><strong>How do you move with Vim?</strong></Summary>

    ###
    - `h`: left
</details>

49. <details>
    <Summary><strong>How do you move with Vim?</strong></Summary>

    ###
    - `h`: left
</details>

50. <details>
    <Summary><strong>How do you move with Vim?</strong></Summary>

    ###
    - `h`: left
</details>
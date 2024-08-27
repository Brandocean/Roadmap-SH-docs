[⏪ Return to index ⏪](./README.md)

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

## Editing Files

1. <details>
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

2. <details>
    <Summary><strong>What are the differences between nano and vi/vim?</strong></Summary>

    ###
    - `nano` is a basic text editor, which is easy to use and perfect for simple text file editing. 
    - `Vi/vim`, on the other hand, is more advanced and offers a wide range of features and commands.
</details>

3. <details>
    <Summary><strong>How do you save files with nano?</strong></Summary>

    ###
    - `Ctrl + O`.
</details>

4. <details>
    <Summary><strong>How do you exit nano?</strong></Summary>

    ###
    - `Ctrl + X`.
</details>

5. <details>
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

6. <details>
    <Summary><strong>How do we move between buffers with nano?</strong></Summary>

    ###
    - `Atl + >` or `Alt + <`.
</details>

7. <details>
    <Summary><strong>How do we copy and paste sections in our nano file?</strong></Summary>

    ###
    - To select your text use `Alt + A`
    - To copy select your text and use `Alt + ^`.
    - To paste just type `Ctrl + U`.
    - To cut select your text and use `Ctrl + K` 
</details>

8. <details>
    <Summary><strong>How do we move to the top and bottom of a file with nano?</strong></Summary>

    ###
    - `Alt + \` to go to the top.
    - `Alt + /` to go to the bottom.
</details>

9. <details>
    <Summary><strong>How do we search and replace words with nano?</strong></Summary>

    ###
    - To search type `Ctrl + W`, type the word you want to search and press Enter.
        - Do this many times to go through all the findings. 
    - To replace type `Alt + R`, type the word and the new-word and type enter
        - Type `yes` or `no` to check each finding or `A` to change all the findings.
</details>

10. <details>
    <Summary><strong>What are the three modes of Vim?</strong></Summary>

    ###
    - Normal: for navigation and manipulation.
    - Insert: for editing text.
    - Command: for executing commands.
</details>

11. <details>
    <Summary><strong>How do we write content with Vim?</strong></Summary>

    ###
    - Type `i` to get into INSERT mode.
</details>

12. <details>
    <Summary><strong>How do we save and quit a file with Vim?</strong></Summary>

    ###
    - `:wq` where `:w` is for save and `:q` is for quit.
    - Also you can use `ZZ`.
    - `:w FILE_NAME` if you want to create a new file with the actual information.
</details>

13. <details>
    <Summary><strong>How do we copy and paste with Vim?</strong></Summary>

    ###
    - Type `v` to enter the visual mode, select the section .you want to copy and press `y` to copy or `d` to cut. Finally type `P` to paste.
    - Type `yiw` to copy the current word.
    - Type `yy` to copy the current line or `dd` to delete it and copy.
</details>

14. <details>
    <Summary><strong>How do we repeat commands with Vim?</strong></Summary>

    ###
    - `.` (dot): will repeat the last command.
    - `N<command>`: will repeat the command N times.
        - Example: `2dd` will delete 2 lines.
</details>

15. <details>
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

16. <details>
    <Summary><strong>How do you can see your distribution in Linux?</strong></Summary>

    ###
    ```
    /etc/os-release
    ```
</details>

17. <details>
    <Summary><strong>How do you move with Vim?</strong></Summary>

    ###
    - `h`: left
    - `j`: down (it seems like a ⬇)
    - `k`: up
    - `l`: right
</details>

18. <details>
    <Summary><strong>How do we add content that is in another file with Vim?</strong></Summary>

    ###
    - In the Normal mode type: `r FILE_NAME`
</details>

19. <details>
    <Summary><strong>How can we run linux command with Vim?</strong></Summary>

    ###
    - In command mode type: `! LINUX_COMMAND`
    - Example: `! ls`
</details>

20. <details>
    <Summary><strong>What is a buffer?</strong></Summary>

    ###
    - A buffer is a chunk of memory that holds the text of a file that you're currently editing.
    - Example: When you open a new vim file you are in a new buffer.
</details>

21. <details>
    <Summary><strong>How move between buffers?</strong></Summary>

    ###
    - `bp`: to move to the previous buffer (buffer previous)
    - `bn`: to move to the next buffer (buffer next)
    - `bd`: if you want to delete the actual buffer
    - `badd`: if you want to add a buffer without switch (remains in the actual buffer).
</details>

22. <details>
    <Summary><strong>How do you we create a new buffer with Vim?</strong></Summary>

    ###
    - `:enew`: to create an empty buffer
</details>

23. <details>
    <Summary><strong>How do we find and replace with Vim?</strong></Summary>

    ###
    - `%s/OLD_WORD/NEW_WORD/g`:
    - If you only want to find type until OLD_WORD 
</details>

24. <details>
    <Summary><strong>How do we split with Vim?</strong></Summary>

    ###
    - `:split FILE_NAME` or `:sp FILE_NAME`: for horizontal split (or open two files in the same terminal window).
        - `vim -o FILE1 FILE2`: to open the files with this config.
    - `:vsplit FILE_NAME` or `:vsp FILE_NAME`: for vertical split (recommended).
        - `vim -O FILE1 FILE2`: to open the files with this config.
    - `Ctrl + ww`: to move between files.
    - `:q` to exit one buffer.
</details>

25. <details>
    <Summary><strong>How do we active line numbers in Vim?</strong></Summary>

    ###
    `:set number`: to active line numbers
    `:set nonumber`: to deactivate line numbers
</details>

26. <details>
    <Summary><strong>How do we configure Vim?</strong></Summary>

    ###
    - Open the file `.vimrc` in your home directory (/home/brandocean for example) and write the configuration that you want.
        - If you don't open the file in your home directory, changes would not be made.
    - Example: `set number` to have the line numbers each time we open a vim file.
</details>
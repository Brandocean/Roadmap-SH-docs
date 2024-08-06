# Linux Roadmap
> Link to [Linux roadmap.sh](https://roadmap.sh/linux)

## Navigation basics

1. <details>
    <Summary><strong>What command do we use to change directories?</strong></Summary>

    ```console
    cd /path/to/directory
    ```
</details>

2. <details>
    <Summary><strong>What command do we use to list the contents of a directory?</strong></Summary>

    ```console 
    ls
    ```
</details>

3. <details>
    <Summary><strong>What command do we use to view current working directory?</strong></Summary>

    ```console 
    pwd
    ```
</details>

4. <details>
    <Summary><strong>What command do we use to display the mannual page for a command?</strong></Summary>

    ```console 
    man ls
    ```
</details>

5. <details>
    <Summary><strong>What command do we use to move files in Linux?</strong></Summary>

    ```console 
    mv [options] source destination
    ```
    - **source**: Is the directory you want to move
    - **destination**: Is where you want to move your source file
    - You can use this command without the [options] part

    > [!NOTE]
    > You can use it also to rename files for example `mv file.txt file2.txt` this gonna change the name of file.txt.
</details>

6. <details>
    <Summary><strong>How do we create files in Linux?</strong></Summary>

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

    >[!NOTE]
    > The command echo itself only shows the string on console `echo "This is a file"`
</details>

7. <details>
    <Summary><strong>How do we delete files in Linux?</strong></Summary>

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

    - Also known as the Filesystem Hierarchy Standard (FHS), is a defined tree structure that helps to prevent files from being scattered all over the system and organize them in a logical and easy-to-navigate manner.
</details>

9. <details>
    <Summary><strong>What is the structure of the Filesystem Hierarchy Standard?</strong></Summary>

    - **/:** Root directory, the top level of the file system.
    - **/home:** User home directories.
    - **/bin:** Essential binary executables.
    - **/sbin:** System administration binaries.
    - **/etc:** Configuration files.
    - **/var:** Variable data (logs, spool files).
    - **/usr:** User programs and data.
    - **/lib:** Shared libraries.
    - **/tmp:** Temporary files.
</details>
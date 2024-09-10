[⏪ Return to index ⏪](./README.md)

<details>
<Summary><strong>Files</strong></Summary>

- [awk documentation](https://www.gnu.org/software/gawk/manual/html_node/index.html#SEC_Contents)
- [Practice awk](https://linuxhandbook.com/awk-command-tutorial/#9-a-simple-example-of-awk-array)
- [Ripgrep github](https://github.com/BurntSushi/ripgrep)
- [Advanced grep topics](https://caspar.bgsu.edu/~courses/Stats/Labs/Handouts/grepadvanced.htm)
</details>

## Text Processing

1. <details>
    <Summary><strong>What is awk?</strong></Summary>

    ###
    - `awk` is a powerful text-processing language.
    - Named after its three original developers - Alfred Aho, Peter Weinberger, and Brian Kernighan.
    - awk is adept at performing operations upon text files, such as sorting, filtering, and report generation.
</details>

2. <details>
    <Summary><strong>How awk programs are made of?</strong></Summary>

    ###
    - AWK programs are made of one or many `pattern { action }` statements.
</details>

3. <details>
    <Summary><strong>How do we print the first column of the <code>ps</code> using awk?</strong></Summary>

    ###
    - `ps | awk '{print $1}'`: To print the first command.
    - `ps | awk '{print $0}'` or `awk '{print}'` will print everything like normal ps or cat with files
</details>

4. <details>
    <Summary><strong>What are the main pre-defined variables in awk?</strong></Summary>

    ###
    - `RS`: The record separator. AWK processes your data one record at a time. By default, this is the newline character.
    - `NR`: The current input record number. If you use the newline in `RS` this will be the line number.
    - `FS/OFS`: The character(s) used as the field separator. Once AWK reads a record, it splits it into different fields based on the value of `FS`. When AWK print a record on the output, it will rejoin the fields, but this time, using the `OFS` separator instead of the FS separator.
        - “white space” is the default value for both of them.
        - `FS` to read and `OFS` to display records.
    - `NF`: The number of fields in the current record. If you use the “white space” for `FS/OFS` it will be the number of words in the current record
</details>

5. <details>
    <Summary><strong>How do we remove a file header with awk?</strong></Summary>

    ###
    - `awk 'NR>1' FILE_NAME`
    - Or `awk 'NR>1 { print }' FILE_NAME`
    - Here we say "print the line numbers above 1."
</details>

6. <details>
    <Summary><strong>How do we print lines in range with awk?</strong></Summary>

    ###
    - For example: `awk 'NR>1 && NR<4' FILE_NAME`
    - Here we say "print the lines between 1 and 4" that it will be line 2 and line 3.
</details>

7. <details>
    <Summary><strong>How do we remove whitespace-only lines with awk?</strong></Summary>

    ###
    - `awk 'NF' FILE_NAME`
</details>

8. <details>
    <Summary><strong>How do we extract fields with awk?</strong></Summary>

    ###
    - `awk '{ print $1 $3 }' FILE_NAME` to print column 1 and 3,
    - `awk '{ print $1 $3}' FS=, OFS=, FILE_NAME` to print column 1 and 3 but using the comma as a separator instead of a white space.
    
    > You can also use the 
</details>

9. <details>
    <Summary><strong>How do we use the BEGIN and END block?</strong></Summary>

    ###
    - We use `BEGIN` to initialize variables before the first record is read.
        - For example `awk 'BEGIN { FS=OFS="," } NF { print $1, $3 }' file`
    - We use `END` blocks to perform some tasks after the last record has been read.
        - For example `awk '{ SUM+=$1 } END { print SUM }' FS=, OFS=, file`
</details>

10. <details>
    <Summary><strong>How do we perform calculations column-wise?</strong></Summary>

    ###
    - For example: `awk '{ SUM=SUM+$1 } END { print SUM }' FS=, OFS=, file` or `awk '{ SUM+=$1 } END { print SUM }' FS=, OFS=, file` where we use `+=`.
    - Here we sum all the values in the first column and if there is a whitespace or text it will be considered as `0` so the sum isn't affected. But maybe with multiplications will.
</details>

11. <details>
    <Summary><strong>How do we count the number of non-empty lines?</strong></Summary>

    ###
    - `awk '/./ { COUNT+=1 } END { print COUNT }' file`: This only ignore blank lines.
        - `/./` this is a regular expresion that say if contain at least one character (the pattern is inside the `/` and if you wanna use `/` you need to add this `\/`).
    - `awk 'NF { COUNT+=1 } END { print COUNT }' file`: This ignore whitespace-only and blank lines.
</details>

12. <details>
    <Summary><strong>How are arrays in awk?</strong></Summary>

    ###
    - Arrays are like maps or dictionaries. For example:
    ```bash
    awk '
    BEGIN {
        # Define an array with three elements
        fruit["apple"] = 10
        fruit["banana"] = 20
        fruit["cherry"] = 30
        
        # Loop through the array and print each key-value pair
        for (item in fruit) {
            print item ": " fruit[item]
        }
    }
    '
    ```
</details>

13. <details>
    <Summary><strong>How can we handle duplicates in arrays with awk?</strong></Summary>

    ###
    - For example `awk 'a[$0]++' FILE_NAME` only shows the duplicates with the `++` operator.
    - To remove the duplicates we use not `!` like this `awk '!a[$0]++' FILE_NAME`
</details>

14. <details>
    <Summary><strong>How do we remove multiple spaces with awk?</strong></Summary>

    ###
    - `awk '$1=$1' FILE_NAME`
</details>

15. <details>
    <Summary><strong>How do we join lines using awk?</strong></Summary>

    ###
    - We use the `ORS`, it means output record separator.
    - `awk '{ print $3 }' FS=, ORS=' ' file; echo`
        - Here we add `; echo` to have a new line while putting that command.
</details>

16. <details>
    <Summary><strong>How do we convert text to upper case using awk?</strong></Summary>

    ###
    - For example: `awk '{ print toupper($0) }' FILE_NAME`
</details>

17. <details>
    <Summary><strong>How do we use boolean expression with awk?</strong></Summary>

    ###
    - For example this line only print the third column only if the first statement it's equal to "fred": `$1 == "fred" { print $3 }`
    - Awk offers a full selection of comparison operators, including the usual "==", "<", ">", "<=", ">=", and "!=". 
    - In addition, awk provides the "~" and "!~" operators, which mean "matches" and "does not match". 
        - For example to print the third column only if the fifth field contains "root": `$5 ~ /root/ { print $3 }`
</details>

18. <details>
    <Summary><strong>How do we do conditional statements with awk?</strong></Summary>

    ###
    - Like the C language, for example:
    ```bash
    { 
        if ( $1 == "foo" ) { 
                if ( $2 == "foo" ) { 
                        print "uno" 
                } else { 
                        print "one" 
                } 
        } else if ($1 == "bar" ) { 
                print "two" 
        } else { 
                print "three" 
        } 
    }
    ```
</details>

19. <details>
    <Summary><strong>How do we count the number of blank lines with awk?</strong></Summary>

    ###
    ```bash
    BEGIN { x=0 } 
    /^$/  { x=x+1 } 
    END   { print "I found " x " blank lines. :)" }
    ```
</details>

20. <details>
    <Summary><strong>Can we use regular expression with FS in awk?</strong></Summary>

    ###
    - Yes, for example `FS="\t+"` or `FS="foo[0‑9][0‑9][0‑9]"`
</details>

21. <details>
    <Summary><strong>What is grep?</strong></Summary>

    ###
    - GREP (Global Regular Expression Print) it is a powerful utility that searches and filters text matching a given pattern.
    - `grep "pattern" FILE_NAME`
</details>

22. <details>
    <Summary><strong>What is ripgrep?</strong></Summary>

    ###
    - `ripgrep` is an extremely fast text processor that supports all the features of grep and extends it.
    - Also is a line-oriented search tool that recursively searches the current directory for a regex pattern.
</details>

23. <details>
    <Summary><strong>What is uniq?</strong></Summary>

    ###
    - The `uniq` command allows you to find and filter out duplicate lines, or even provide a count of each unique line in a file.
    - It’s important to remember that `uniq` only removes duplicates that are next to each other, so we sort the data using the `sort` command first.
        - For example: `sort names.txt | uniq`
</details>

24. <details>
    <Summary><strong>Explain the expand and unexpand command</strong></Summary>

    ###
    - `expand FILE_NAME`: Is a command that converts tabs into spaces.
    - `unexpand FILE_NAME`: Is a command that converts spaces into tabs.
    - We can verify by creating a new file for example `expand file1 > file2` and use `cat -A file2` where if we see `^I` are tabs and if we don't see nothing, there are spaces.
</details>

25. <details>
    <Summary><strong>What is the default value of tabs with expand?</strong></Summary>

    ###
    - The `expand` command by default converts tabs into 8 spaces.
    - To specify the number of spaces for each tab, the `-t` option can be used as follows: `expand -t 4 FILE_NAME`
    - It also works with the unexpand `unexpand -t 4 FILE_NAME` to change 4 spaces into a tab.
</details>

26. <details>
    <Summary><strong>Explain the wc command</strong></Summary>

    ###
    - The `wc` command allows users to count the number of bytes, characters, words, and lines in a file or in data piped from standard input.
    - The name wc stands for ‘word count’ but it can do much more.
    - The basic usage is `wc FILE_NAME`
</details>

27. <details>
    <Summary><strong>Explain the output of the wc command</strong></Summary>

    ###
    - This command would output the number of lines, words, and characters in test.txt. 
    - For example: ` 1  5 28 test.txt`
</details>

28. <details>
    <Summary><strong>Explain the nl command</strong></Summary>

    ###
    - `nl` command is a utility for numbering lines in a text file. Also known as ‘number lines’ (Is like a cat but with number lines).
    - Basic sintax: `nl [options] FILE_NAME`
    - If no file is specified, nl will wait for input from user’s terminal (stdin), you can check multiple files with this method because it's like a while true waiting for more inputs of file names.
</details>

29. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

30. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

31. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

32. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

33. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

34. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

35. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

36. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

37. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

38. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

39. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

40. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

41. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

42. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

43. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

44. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

45. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

46. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

47. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

48. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

49. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>

50. <details>
    <Summary><strong>Question?</strong></Summary>

    ###
    - Answer
</details>
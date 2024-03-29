# File Comparison Commands

We can compare data of two files by using the following commands:

1. **cmp Command:**
   - It will compare byte by byte.
     ```
     cmp file1.txt file2.txt
     ```
   - If content is the same, then no output.
   - If the content is different, then it provides information about only the first difference. Byte number and line number will be provided.
     ```
     $ cmp a.txt c.txt
     a.txt c.txt differ: byte 7, line 2
     ```
   - Note: cmp command won't show all differences and show only the first difference.

2. **diff Command:**
   - It will show all differences in the content.
     ```
     diff file1.txt file2.txt
     ```
   - If the content is the same, then no output.
   - If the content is different, then it will show all differences.
   
   For the diff command, we can use the following options:
   - `-q`: shows message when files are different.
   - `-s`: shows message when files are same or identical.
   - `-y`: shows comparison line by line (parallel comparison).

3. **sdiff Command:**
   - We can use the sdiff command for side-by-side comparison (parallel comparison).
   - Note: sdiff command and diff command with -y option are the same.

4. **vimdiff Command:**
   - It will highlight differences in vim.
   - To support this command, we have to install vim by using the following command:
     ```
     sudo apt install vim
     ```
   - ```
     vimdiff a.txt b.txt
     ```
   - `ctrl+w+w`: To go to the next window.
   - `:q`: Close the current window.
   - `:qa`: Close all windows.
   - `:qa!`: Close all windows forcibly.

5. **comm Command:**
   - By using this command, we can compare the data of two files.
     ```
     comm file1.txt file2.txt
     ```
   - It displays results in 3 columns:
     - Column-1: Data present only in file1.txt but not in file2.txt.
     - Column-2: Data present only in file2.txt but not in file1.txt.
     - Column-3: Common data of both files.


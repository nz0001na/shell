# Shell Command
A small summary of shell command used.

A website for shell command explanation: https://explainshell.com/


# To get the total number of files in the current folder using the command terminal, you can use the following command:
  bash:
  
        ls -1 | wc -l
        
Explanation:

* ls -1: This command lists all files and directories in a single column format.
* wc -l: This counts the number of lines in the output from the ls command, effectively giving you the total number of files and directories.

Note:

This command counts all files and directories, including hidden files (those starting with a dot). If you want to count only non-hidden files, you can use:

bash:

    ls -1A | wc -l
    
Here, the -A option includes hidden files but excludes the . and .. entries.

If you want to count only files (excluding directories), you can use:

bash:

    find . -maxdepth 1 -type f | wc -l
    
This command uses find to look for files (-type f) in the current directory (.) without descending into subdirectories (-maxdepth 1).

# Monitor the system’s vital resources or server’s processes

a command line utility that allows the user to interactively monitor the system’s vital resources or server’s processes in real time.

     htop [-dChusv]
   
https://www.geeksforgeeks.org/htop-command-in-linux-with-examples/


# Print System Information

      uname -a

Displays the name of the current operating system.

https://www.ibm.com/docs/ru/aix/7.1?topic=u-uname-command

# 4. How to list a part of files in a foler in shell
To list a part of the files in a folder using the shell, you can use various commands depending on your specific needs. Here are a few methods:
* (1). Using ls with Wildcards

You can use the ls command along with wildcards to filter the files you want to list. For example, to list all .txt files in the current directory:

bash

    ls *.txt
    
* (2). Using find
  
The find command is powerful for searching files based on specific criteria. To list files that start with "file" in the current directory:

bash

    find . -maxdepth 1 -type f -name "file*"
    
* (3). Using grep with ls
  
If you want to list files based on a pattern in their names, you can combine ls with grep. For example, to list files containing "report":

bash

    ls | grep "report"
    
* (4). Limiting Output with head or tail
  
If you want to list only a certain number of files, you can pipe the output to head or tail. For example, to list the first 5 files:

bash

    ls | head -n 5
    
* (5). Using printf
  
You can also use printf to format the output. For example, to list all files with a specific extension:

bash

    printf '%s\n' *.jpg

These commands provide flexibility in listing files based on your requirements in the shell. If you have a specific scenario in mind, feel free to ask for more tailored commands!

# unzip a file
    $unzip filename.zip
    $tar -xvzf filename.tar.gz
























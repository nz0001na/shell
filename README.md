# Shell Command
A small summary of shell command used.

# 1. To get the total number of files in the current folder using the command terminal, you can use the following command:
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

# htop: Monitor the system’s vital resources or server’s processes

a command line utility that allows the user to interactively monitor the system’s vital resources or server’s processes in real time.

https://www.geeksforgeeks.org/htop-command-in-linux-with-examples/



























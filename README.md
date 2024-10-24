# Shell Command
A small summary of shell command used.

A website for shell command explanation: https://explainshell.com/

**************************************************************************************************************************













# Create folders

To make a single folder, type the following command, replacing "FolderName" with the name you want to assign to your folder. Then, press Enter.

        mkdir FolderName

To create a folder that has spaces in its name, enclose the name with double quotes like this:

        mkdir “Mahesh Makvana”

To create a folder inside a folder is to specify the other folder right in the mkdir command itself. For example, if you have a subfolder named "Photos" and you want to create a new folder named "Personal" inside it, use the following command:

        mkdir Photos\Personal

To make several folders at once, add the required folder names to the mkdir command. For example, to create three separate folders named Documents, Photos, and Videos, use the following command:

      mkdir Documents Photos Videos


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
    
# move files
        $mv ~/Downloads/*.mp3 ~/Music/

# download a file given a URL
        $wget url


# Copying directories (cp command)
Use the cp command to create a copy of the contents of the file or directory specified by the SourceFile or SourceDirectory parameters into the file or directory specified by the TargetFile or TargetDirectory parameters.

If the file specified as the TargetFile exists, the copy writes over the original contents of the file. If you are copying more than one SourceFile, the target must be a directory.

To place a copy of the SourceFile into a directory, specify a path to an existing directory for the TargetDirectory parameter. Files maintain their respective names when copied to a directory unless you specify a new file name at the end of the path. The cp command also copies entire directories into other directories if you specify the -r or -R flags.

The following are examples of how to use the cp command:
To copy all the files in the /home/accounts/customers/orders directory to the /home/accounts/customers/shipments directory, type the following:
        
        cp /home/accounts/customers/orders/* /home/accounts/customers/shipments

This copies the files, but not the directories, from the orders directory into the shipments directory.
To copy a directory, including all its files and subdirectories, to another directory, type the following:

        cp -R /home/accounts/customers /home/accounts/vendors

This copies the customers directory, including all its files, subdirectories, and the files in those subdirectories, into the vendors directory.























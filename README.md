# Shell Command
A small summary of shell command used.

A website for shell command explanation: https://explainshell.com/

**************************************************************************************************************************

## How to unzip a bunch of .tar.gz files in a same directory using command?

To unzip a bunch of .tar.gz files in the same directory using a single command, you can use a for loop in the terminal. Here's how:

Command to Extract All .tar.gz Files in a Directory.

Run the following command in the terminal:

              for file in *.tar.gz; do tar -xzf "$file"; done

Explanation:

              for file in *.tar.gz: Loops through all files in the current directory that have the .tar.gz extension.
              tar -xzf "$file": Extracts each .tar.gz file one by one.
              -x: Extracts the files.
              -z: Handles the gzip compression.
              -f: Specifies the file to extract.
              "$file": Ensures the file name is correctly passed to the tar command, even if it contains spaces.

Extracting to a Specific Directory

If you want to extract all .tar.gz files into a specific directory, you can modify the command:
           
            for file in *.tar.gz; do tar -xzf "$file" -C /path/to/destination; done

Replace /path/to/destination with the directory where you want the files to be extracted.

Alternative Using find

If the .tar.gz files are located in subdirectories as well, you can use the find command:
           
            find . -name "*.tar.gz" -exec tar -xzf {} \;

Explanation:
          
          find . -name "*.tar.gz": Searches for all .tar.gz files in the current directory and its subdirectories.
          -exec tar -xzf {}: Executes the tar command on each file found.
          \;: Ends the -exec command.

Notes:

Be Cautious: Ensure you are in the correct directory before running these commands to avoid extracting files in unintended locations.
Error Handling: If a .tar.gz file is corrupted, the loop will continue extracting the remaining files.
This approach is efficient and works well for batch extraction of .tar.gz files!


## How to unzip .tar file using bash terminal command

To unzip a .tar file using the bash terminal, you can use the tar command. Here's how:

Basic Command to Extract a .tar File

To extract the contents of a .tar file, use the following command:

                tar -xvf filename.tar
                -x: Extracts the files.
                -v: Displays the progress in the terminal (optional).
                -f: Specifies the file to extract.
For example:

                tar -xvf archive.tar
This will extract all the files and directories from archive.tar into the current directory.

Extracting to a Specific Directory

If you want to extract the .tar file to a specific directory, use the -C option:
                
                tar -xvf filename.tar -C /path/to/destination
For example:

                tar -xvf archive.tar -C /home/user/documents

This will extract the contents of archive.tar into /home/user/documents.

Listing the Contents Without Extracting

To see the contents of a .tar file without extracting it, use the -t option:
                tar -tvf filename.tar

This will display a list of files and directories inside the .tar file.

Additional Notes:

If the file is compressed (e.g., .tar.gz or .tar.bz2), you will need additional options to handle the compression. For example:

                .tar.gz: Use tar -xzvf filename.tar.gz.
                .tar.bz2: Use tar -xjvf filename.tar.bz2.
                
Always ensure you are in the correct directory or specify the full path to the .tar file when running the command.
By following these steps, you can easily extract .tar files using the terminal!


## Create folders

To make a single folder, type the following command, replacing "FolderName" with the name you want to assign to your folder. Then, press Enter.

        mkdir FolderName

To create a folder that has spaces in its name, enclose the name with double quotes like this:

        mkdir “Mahesh Makvana”

To create a folder inside a folder is to specify the other folder right in the mkdir command itself. For example, if you have a subfolder named "Photos" and you want to create a new folder named "Personal" inside it, use the following command:

        mkdir Photos\Personal

To make several folders at once, add the required folder names to the mkdir command. For example, to create three separate folders named Documents, Photos, and Videos, use the following command:

      mkdir Documents Photos Videos


## To get the total number of files in the current folder using the command terminal, you can use the following command:
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

## Monitor the system’s vital resources or server’s processes

a command line utility that allows the user to interactively monitor the system’s vital resources or server’s processes in real time.

     htop [-dChusv]
   
https://www.geeksforgeeks.org/htop-command-in-linux-with-examples/


## Print System Information

      uname -a

Displays the name of the current operating system.

https://www.ibm.com/docs/ru/aix/7.1?topic=u-uname-command

## How to list a part of files in a foler in shell
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























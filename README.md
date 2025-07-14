# Linux
Linux for DevOps

Directory structure in Linux


Linux Essential Commands:
  i. Navigating the FileSystem.
  ii. File Operations.
  iii. File Permissions.
  iv. View and Edit Files.
  v. Process Management.
  vi. Text Manipulation.
  vii. Input/Output redirections.
  viii. Web Requests.


  i. Navigating the FileSystem:-
    1. PWD --- Print Working Directory.
    2. CD --- Change Directory.
        cd /var/log  -- it is an absolute path. it will change to /var/log directory.
        cd .. -- it will move up one level i.e /var.
        cd ../.. --- it will move up two levels.
        cd ~ --- it will take you to the home directory.
    3. ls --- list directories/files.
       ls -l  -- list directory/file in a long format (Size,date,Permission).
       ls -t -- list directory/file by sorting the modification time.
       ls -a -- list all the directories along with the hidden files.
       ls -lh -- Human readable format.
       ls -R -- Recursive listing. Which will show all the files in each of the directories in that particular directory.
       ls -S -- sorts the listing of directories/files according to the size. Largest size at first.
       ls -r -- display the list in reverse order. we can use this combination of reversing with other option like -t, -S.
    4. Which <command name>  -- it finds the executable paths of the command.
         example which ls , which python3, which grep etc.
    5. Find  --- this command is used to find the files and directories.
       find /home -name '*.txt' --- finds all the text files in /home directory and all of its subdirectories.
       find /home -iname '*.TXT' --- to make it case insensitive we will use -iname.
       find /home -maxdepth 2 -name '*.txt' --- to limit the search to 2 levels only i.e /home and its immideate subdirectory.
       find /home -type f -name '*.txt' --- limit the search only to file type
       find /home -name '*.txt' -mtime -7 --- find files which are modified within 7days.
       find /home -name '*.txt' -mtime +30 -- find files which are modified over 30 days.
       find /home -name '*.txt' -size +1M --- find files larger than 1megabytes.
       find /home -name '*.txt' -size -10k -- find files smaller than 10 kilobytes.
       find /home -name '*.txt' -exec rm -v {} \; -- find the txt files and delete. -exec will execute the rm(remove) commandon the files. -v makes rm to print the file name after each deletion. {} is a placeholder for filename. \ terminates the command. 
       find /home -name '*.txt' -exec grep -l "error" {} \; --- prints the file names which containing error.
       find /home -name '*.txt' -exec gzip {} \; --- Gzips the txt files individually 
       find /home -name '*.txt' -exec chmod 755 {} \; -- makes all files executable.
       find /home -name '*.txt' -exec cp {} /backup \;  -- all the txt files will be copied to backup.
       find /home -name '*.txt' -ok rm -v {} \;   --- it will ask before each deletion. so it is better to use -ok instead of -exec for deletion.
      **** find /home -name '*.txt' -print0 | xargs -0 rm -v --- here it will find all the .txt files and -print0 is a special output format which uses NULL character(\0) as a seperator for the filenames instead of newline. These will be passed to the xargus as an input. the xargs converts the input into command argument. -0 tells the xargs to accept the NULL seperated input (matches to -print0). --- this commands work faster than the exec rm , because it groups multiple filenames into single argument and execute the rm command once on them.
    6. whereis --- finds binaries, sources and manpages
    7. mkdir -- creates the directories.
    8. rmdir -- remove the empty directories.
       rm -r --- deletes recursively.
       rm -rf -- deletes forcefully.

  ii. FileOperations.
    1. 





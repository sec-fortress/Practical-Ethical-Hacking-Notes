_Here are Top Commad used in Navigating the linux file system:_

`pwd` (Print Working Directory):

- - Explanation: Displays the current working directory.
    - Example: Running `pwd` in the terminal would show the absolute path of the current directory, such as "/home/user/documents".

`cd` (Change Directory):

- - Explanation: Allows you to change the current working directory.
    - Example: Running `cd /home/user/documents` would change the directory to "/home/user/documents".

`cd ..` (Change to Parent Directory):

- - Explanation: Moves up one level in the directory hierarchy.
    - Example: Running `cd ..` in "/home/user/documents" would move to the "/home/user" directory.

`ls` (List Directory Contents):

- - Explanation: Lists the files and directories in the current directory.
    - Example: Running `ls` would display the files and directories in the current directory.

`ls -la` (List Detailed Directory Contents):

- - Explanation: Lists detailed information about files and directories, including hidden files.
    - Example: Running `ls -la` would display a detailed list of files and directories, including hidden files, in the current directory.

`mkdir` (Make Directory):

- - Explanation: Creates a new directory.
    - Example: Running `mkdir new_folder` would create a new directory named "new_folder" in the current directory.

`rmdir` (Remove Directory):

- - Explanation: Removes an empty directory.
    - Example: Running `rmdir empty_folder` would remove the directory named "empty_folder" if it is empty.

`man` (Manual):

- - Explanation: Displays the manual pages for a specified command.
    - Example: Running `man ls` would show the manual pages with detailed information about the `ls` command.

`echo`:

- - Explanation: Displays text or variables as output.
    - Example: Running `echo "Hello, world!"` would output "Hello, world!" in the terminal.

`>` (Output Redirection):

- - Explanation: Redirects the output of a command to a file and overwrites the file if it already exists.
    - Example: Running `echo "Hello" > greeting.txt` would write the text "Hello" to a file named "greeting.txt" or overwrite the file if it exists.

`>>` (Append Output):

- - Explanation: Redirects the output of a command and appends it to a file.
    - Example: Running `echo "World!" >> greeting.txt` would append the text "World!" to the end of the "greeting.txt" file.

`rm` (Remove):

- - Explanation: Deletes files or directories.
    - Example: Running `rm file.txt` would delete the file named "file.txt" from the current directory.

`mv` (Move):

- - Explanation: Moves or renames files and directories.
    - Example: Running `mv file.txt new_directory/file_renamed.txt` would move the file "file.txt" to the "new_directory" and rename it as "file_renamed.txt".

`cp` (Copy):

- - Explanation: Copies files and directories.
    - Example: Running `cp file.txt backup/file_copy.txt` would create a copy of "file.txt" named "file_copy.txt" in the "backup" directory.

`locate`:

- - Explanation: Searches for files and directories in a prebuilt database.
    - Example: Running `locate myfile.txt` would search for the file named "myfile.txt" in the prebuilt database and display its path if found.

`updatedb`:

- - Explanation: Updates the database used by the `locate` command to reflect recent changes in the file system.
    - Example: Running `updatedb` would update the database, allowing the `locate` command to provide up-to-date search results.

`passwd`:

- - Explanation: Allows a user to change their password.
    - Example: Running `passwd` would prompt the user to enter their current password and then set a new password.

### NOTE </3
Remember to exercise caution when using commands like `rm` as they can permanently delete files. It's always a good practice to double-check before executing such commands.
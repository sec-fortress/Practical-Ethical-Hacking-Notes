## What does it do?
The `sudo` command in Linux allows a user with appropriate privileges to execute commands as a superuser or another user. It is commonly used to perform administrative tasks that require elevated privileges. Here's an example of how `sudo` is used:

## How to Use </3
Let's say you want to install a software package using the `apt` package manager, but it requires administrative privileges. You can use `sudo` to execute the `apt` command with elevated privileges. Here's the command:

```zsh
sudo apt install <package_name> 
```


For instance, if you want to install the package named "nginx" on an Ubuntu system, you can use the following command:

```zsh
sudo apt install nginx 
```

After running this command, you will be prompted to enter your password. Once you provide the correct password, the command will be executed with superuser privileges, allowing you to install the "nginx" package on the system.

Please note that the availability and configuration of `sudo` can vary depending on the Linux distribution and the user's privileges. Additionally, the `sudo` command can be used for various other administrative tasks, such as editing system files, managing services, and executing critical commands.

**_Here are explanations and examples of the commands mentioned Below:_**

`sudo service apache2 start`:

- - Explanation: Starts the Apache web server service.
    - Example: Running `sudo service apache2 start` would initiate the Apache web server and make it available for serving web pages.

`sudo service apache2 stop`:

- - Explanation: Stops the Apache web server service.
    - Example: Running `sudo service apache2 stop` would halt the running Apache web server, shutting down any active web page serving.

`python3 -m http.server 80`:

- - Explanation: Starts a simple HTTP server using Python on port 80.
    - Example: Running `python3 -m http.server 80` would start a basic HTTP server on port 80, allowing you to serve files from the current directory.

`sudo systemctl enable ssh`:

- - Explanation: Enables the SSH (Secure Shell) service to start automatically on system boot.
    - Example: Running `sudo systemctl enable ssh` would configure the system to start the SSH service during system startup.

`sudo systemctl disable ssh`:

- - Explanation: Disables the SSH service from starting automatically on system boot.
    - Example: Running `sudo systemctl disable ssh` would prevent the SSH service from starting automatically during system startup.

### NOTE </3
These commands are frequently used in Linux systems for managing services, starting and stopping processes, and enabling or disabling specific services at system startup. The `sudo` command is used to execute commands with superuser privileges. The `service` and `systemctl` commands are used to manage system services.
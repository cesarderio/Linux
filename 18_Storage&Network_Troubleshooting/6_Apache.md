# Troubleshooting the Apache Web Server in Linux

<br>

## Verifying Apache Installation and Operation

- **Check Installation**: Use `sudo apt install apache2` to verify if Apache is already installed.
- **Update Packages**: Ensure all packages are up-to-date with `sudo apt update` and `sudo apt upgrade`.
- **Check Service Status**: Confirm if Apache is active and running with `sudo service apache2 status`.

<br>

## Testing Web Server Accessibility

- **Verify IP Address**: Use `ip a` to find the server's IP address.
- **Testing with Curl**: Use `curl http://[server-ip]` to test if the default Apache web page is accessible.

<br>

## Addressing Port Conflicts

- **Identify Port Usage**: If Apache fails to start, check if port 80 is in use (e.g., by Docker containers).
- **Stop Conflicting Services**: Use `sudo docker stop [container_name]` to stop services occupying port 80.
- **Restart Apache**: After resolving port conflicts, start Apache with `sudo service apache2 start`.

<br>

## Configuration File Management

- **Editing Ports Configuration**: Modify the `ports.conf` file in `/etc/apache2` to change listening ports.
- **Checking File Permissions**: Verify the Apache binary permissions with `ll /usr/sbin/apache2`.

<br>

## User Account Management

- **Identify Running User**: Use `ps aux | egrep '(apache | httpd)'` to see under which user Apache is running.
- **Process Tree Analysis**: Utilize `pstree` or `pstree -p` to view Apache's process hierarchy.

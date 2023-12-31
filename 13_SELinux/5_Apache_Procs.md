# Managing SELinux for Apache Process and File Access

<br>

## Introduction to SELinux Management for Apache

In this demonstration, we explore how to manage an Apache process and its associated files under SELinux's enforcing mode. We'll examine process contexts and adjust file contexts to ensure proper access.

<br>

### Verifying Apache Process Context

1. **Viewing Process Context**: Run `ps -auxZ | grep apache2` to display Apache's process context. Apache processes typically have a context type like `httpd_t`.
2. **Checking File Context**: Use `ls -Z /usr/sbin` to view the binary initiating the Apache daemon. It should have a context type `httpd_exec_t`.

<br>

### Setting Up an Apache Site in SELinux

1. **Creating a Website Directory**: Execute `sudo mkdir /mysite` to create a new directory for hosting a website.
2. **Adding an HTML File**: Create an `index.html` file in `/mysite` with basic HTML content.
3. **Configuring Apache**: Modify the Apache configuration file to set `/mysite` as the DocumentRoot.
4. **Restarting Apache**: Apply changes by restarting Apache with `sudo service apache2 restart`.

<br>

### Troubleshooting SELinux Enforcing Mode

1. **Switching SELinux Mode**: Transition between permissive (`sudo setenforce 0`) and enforcing (`sudo setenforce 1`) modes.
2. **Testing Web Access**: Verify if the Apache server serves the webpage correctly in both modes. In enforcing mode, incorrect contexts can lead to access denial.
3. **Correcting File Context**: If access is denied, check the context of `/mysite/index.html` using `ls -Z`. The file might have a `default_t` type.
4. **Changing File Context**: To rectify, use `sudo chcon -t httpd_sys_content_t /mysite` to change the context to `httpd_sys_content_t`. Ensure the Apache process can access the directory and files.

<br>

### Verifying Access in Enforcing Mode

- After modifying the file context, refresh the webpage in the browser while SELinux is in enforcing mode. If configured correctly, the Apache server should serve the `index.html` without any permission issues.

<br>

## Conclusion

Managing SELinux for an Apache server involves careful consideration of process and file contexts. In enforcing mode, SELinux restricts access based on these contexts, and incorrect configurations can lead to resource access issues. Adjusting file contexts to align with the Apache process context is crucial for seamless operation. This demonstration highlights the importance of understanding SELinux policies and their impact on system processes and file access.

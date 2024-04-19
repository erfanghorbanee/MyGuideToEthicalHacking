# Command Injection

**Blind command injection** occurs when the system command made to the server does not return the response to the user in the HTML document.

**Active command** injection will return the response to the user.  It can be made visible through several HTML elements.

## Commands to try

### Linux

- whoami
- id
- ifconfig/ip addr
- uname -a
- ps -ef
- cat /etc/update-motd.d/00-header
- lsb_release -a
- awk -F: '{print $1, $7}' /etc/passwd

### Windows

- whoami
- ver
- ipconfig
- tasklist
- netstat -an

## Tip

To find out the number of non-root, non-service, and non-daemon users on a Linux system, you can use the command line to filter and count users from the `/etc/passwd` file. This file contains a list of all users on the system.

Here is a step-by-step approach:

1. **Open a Terminal:** You will need command line access to the Linux system.

2. **Use `awk` to filter users:** You can use the `awk` command to filter out users based on their UID (User ID) and their shell. Typically, system and daemon users have UIDs less than 1000 (this can vary by distribution) and might use a non-interactive shell like `/bin/false` or `/sbin/nologin`.

3. **Command to find non-root, non-service, and non-daemon users:**

   ```bash
   awk -F: '($3 >= 1000) && $1 != "root" && ($7 == "/bin/bash" || $7 == "/bin/sh")' /etc/passwd | wc -l
   ```

   Explanation:
   - `-F:`: Tells `awk` to use colon (`:`) as the field separator.
   - `($3 >= 1000)`: Filters users with UID 1000 or higher (adjust this number based on your distribution's standards).
   - `$1 != "root"`: Excludes the root user.
   - `($7 == "/bin/bash" || $7 == "/bin/sh")`: Includes users with standard shells (indicative of interactive users).

   The `wc -l` command counts the number of lines output by `awk`, which corresponds to the number of users matching these criteria.

4. **Run the command:** Paste the command into your terminal and press enter. It will display the number of non-root, non-service, and non-daemon users.

This method assumes standard configurations and defaults that might differ between Linux distributions. Adjust the UID threshold and the shell paths as necessary for your specific environment.

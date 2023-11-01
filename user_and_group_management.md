## User and Group Management
### Adding and Manipulating Users and Groups
- `sudo adduser username`: Adds a new user.
- `sudo addgroup groupname`: Creates a new group.
- `sudo adduser user group`: Adds a user to a group (specific to Debian).

### Modifying User Accounts
- `sudo usermod -aG group user`: Adds a user to a group.
- `sudo usermod -rG group user`: Removes a user from a group.

### Listing Users and Groups
- `cat /etc/passwd`, `getent passwd`: Lists user information fields separated by colons.
- `groups`: Lists groups.
- `groups username`: Lists groups to which the username belongs (parses /etc/group).
- `getent group groupname`: Lists users belonging to the groupname (parses system database).

### User Switching and Privilege Management
- `su [username]`: Switches the user to another user (default: root).
- `-`: Switches the user to root (default) with an environment similar to a real login.
- `sudo`: Allows a permitted user to execute a command as the superuser or another user.

### Sudoers Configuration
- `sudo vim(nano) /etc/sudoers` or `su -`, `vim(nano) /etc/sudoers`: Edits the sudoers file without syntax checking.
- `sudo visudo`: Edits the sudoers file with syntax checking.

## Hostname and Configuration
- `/etc/hostname`: File containing mapping information from IP address to domain name.
- `sudo vim /etc/hostname`, `sudo vim /etc/hosts`: Modifies the hostname and hosts file.
- `sudo hostnamectl set-hostname new-hostname`, `sudo vim /etc/hosts`: Modifies the hostname using hostnamectl and the hosts file.
- `sudo hostname new-hostname`: Equivalent to `sudo hostnamectl set-hostname new-hostname`.

#### Hostnames must not include `_`, `@`, `*`, etc.
If you set the hostname including special characters above, the server will have 2 hostnames.
One is the static hostname, which does not include special characters.
The other is the pretty hostname, which may include special characters.
When you execute the `hostnamectl` command, an exception is fired.
However, when you execute the `hostname` command, it outputs an error.

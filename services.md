# services
## SSH (Secure Shell) server
The OpenSSH server provides the necessary components for a system to act as an SSH server.

- `sudo apt install openssh-server -y`: Installs the OpenSSH server and its components.
- `systemctl status ssh`: Checks the SSH service status.
- `sudo systemctl enable ssh`: Enables the SSH service.
- `sudo systemctl start ssh`: Starts the SSH service.
- `/etc/ssh/sshd_config`: SSH daemon configuration file.

## UFW (Uncomplicated Firewall)
UFW is a program for managing a netfilter firewall.

- `sudo apt install ufw -y`: Installs UFW.
- `systemctl status ufw`: Checks the UFW status.
- `sudo systemctl enable ufw`: Enables the UFW service.
- `sudo systemctl start ufw`: Starts the UFW service.

### UFW Usage
- `sudo ufw allow 4242`: Allows access through port 4242 (adds to the whitelist).
- `sudo ufw deny 8080`: Denies access through port 4242 (adds to the blacklist).
- `sudo ufw delete allow 4242`: Deletes the rule allowing port 4242.
- `sudo ufw delete deny 8080`: Deletes the rule denying port 8080.
- `sudo ufw delete [number]`: Deletes the port corresponding to `[number]`.
- `sudo ufw status numberd`: Shows `[number]` of each port.

## cron
time-based job scheduler

* system-wide cron tasks are usually defined in the `/etc/crontab`
* user-specified cron tasks are managed using `crontab` in `/etc/crontab.d/`

### usage
* `sudo crontab -u root -e`: edit crontab file as root user (default: edit `/etc/crontab`)
* `crontab -e`: edit cron tab (edit `/var/spool/cron/crontabs/username`)
* `crontab -l`: list tasks defined by crontab

```
# Example of job definition:
 11 # .---------------- minute (0 - 59)
 12 # |  .------------- hour (0 - 23)
 13 # |  |  .---------- day of month (1 - 31)
 14 # |  |  |  .------- month (1 - 12) OR jan,feb,mar,apr ...
 15 # |  |  |  |  .---- day of week (0 - 6) (Sunday=0 or 7) OR sun,mon,tue,wed,thu,fri,sat
 16 # |  |  |  |  |
 17 # *  *  *  *  * user-name command to be executed 
```

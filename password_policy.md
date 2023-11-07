## Password Policy
- To install the necessary package, run: `sudo apt install libpam-pwquality -y`. 

### /etc/pam.d/common-passwd
- `retry`: Specifies the maximum number of password input attempts.
- `minlen`: Sets the minimum password length requirement.
- `ucredit`: Defines the maximum number of uppercase characters. Using a negative value such as -1 requires users to include at least one uppercase letter in their password.
- `dcredit`: Determines the maximum number of digits that contribute to the password strength. Using a negative value such as -2 requires users to include at least two digits in their password.
- `maxrepeat`: Sets the maximum number of times a single character can be repeated in the password.
- `reject_username`: Ensures that the password does not contain the user's username.
- `difok`: Specifies the minimum number of characters that must differ from the old password.
- `enforce_for_root`: Enforces the same password policy for the root user.

### /etc/login.defs
- `PASS_MAX_DAYS`: Sets the maximum number of days a password can be used before it must be changed.
- `PASS_MIN_DAYS`: Specifies the minimum number of days allowed between password changes.
- `PASS_WARN_AGE`: Sets the number of days of advance warning before a password expires.

Note: Running `sudo reboot` is required for the changes to take effect.

-  `chage -l username`
- if the setting not applied, execute below commands
- `sudo pwunconv`: deletes /etc/shadow
- `sudo pwconv`: creates /etc/shadow
	- /etc/passwd: user account information
	- /etc/shadow: secure user account information

::CentOS Add user & user add in root::

1. Adding a user to the Sudoers file:
- sudo nano /etc/sudoers

2. Creating a new user with Sudo privileges:
- sudo adduser username
- sudo passwd username

3. Now add the user in the “wheel” Group by running the command:
- sudo usermod -aG wheel username



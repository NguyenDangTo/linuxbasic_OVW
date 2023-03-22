### The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.

- **ssh bandit.labs.overthewire.org -p 2220 -l bandit18 "ls"** to ssh to bandit18 and pass a command argument : ls in the last. You will see the file name: readme.

- **ssh bandit.labs.overthewire.org -p 2220 -l bandit18 "cat readme"** we do the same and cat the file readme to get the password for the next level.

### Password: awhqfNnAbc1naukrpqDYcF95h7HoMTrC

### The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on

- **cat sshkey.private** to read the content of sshkey.private. We get private key so we can use it to login to bandit14

- **ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220** to ssh to bandit14 (-i : identity file for public key authentication is read)

- **cat /etc/bandit_pass/bandit14** to get the password.

### Password: fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

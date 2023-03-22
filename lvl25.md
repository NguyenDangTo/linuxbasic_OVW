### Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not /bin/bash, but something else. Find out what it is, how it works and how to break out of it.

- **ls** to list all directories. We got the key bandit26.sshkey.

- **ssh -i bandit26.sshkey bandit26@localhost -p 2220** to login to bandit26. After we get message: `Connection to localhost closed.`

- The shell for user bandit26 is not /bin/bash so we need to check it by cmd: **cat /etc/passwd | grep bandit26** to get default shell in `/usr/bin/showtext`
  so we need to change it to `/bin/bash` to login to bandit26.
- **cat /usr/bin/showtext** we see #!/bin/sh. Because we get `exec more ~/text.txt` so we can use vi to change default shell when we login to bandit26 in more mode.

- **ssh -i bandit26.sshkey bandit26@localhost -p 2220** to ssh and press v to start the editor.
  Inside vim, we can check our current shell by running `:set shell?` and change the shell used in vim for the running session via command: `:set shell=/bin/bash`. After change the shell, we can use `:shell` to get the shell and get the password by cmd: **cat /etc/bandit_pass/bandit26**

### Password: c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1

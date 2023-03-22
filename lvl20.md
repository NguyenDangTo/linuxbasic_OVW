### There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

- **echo "VxCazJaVykI6W36BkBU0mJTCM8rR95XT" | nc -l -p 2000 &**

1. **echo "VxCazJaVykI6W36BkBU0mJTCM8rR95XT"** to read the password of bandit20.
2. **nc -l -p 2003** to make a server listen on port 2003 (-l: listen, -p: port).
3. **&** to run the command in the background.

So we can make a server that listens on port 2003 and get the password of bandit20.

- **./suconnect 2003** to run the setuid binary and connect to the server on port 2003. Then it read a line of text from the connection and compares it to the password in the previous level (we have send the password by echo for it). If the password is correct, it will transmit the password for the next level (bandit21). So we get the password for the next level.

### Password: NvEJF7oVjkddltPSrdKEFOllh9V1IBcq

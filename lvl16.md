### The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

- **nmap -p 31000-32000 localhost** we get list 5 of ports open. Test all ports and we get port 31790

- **mkdir /tmp/dangto** to make a temporary directory to work in it.

- **cd /tmp/dangto** get to directory dangto

- **echo JQttfApK4SeyHwDlI9SXGR50qclOAil1 | openssl s_client -connect localhost:31790 -quiet > /tmp/dangto/sshkey.private** to connect to localhost on port 31790 and get the private key then save to sshkey.private.

- **ssh -i sshkey.private bandit17@localhost -p 2220** to submit the sshkey to the localhost port 2220 by ssl encryption to login to the next level.

### Password: JQttfApK4SeyHwDlI9SXGR50qclOAil1

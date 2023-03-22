### A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.You do not need to create new connections each time

- **mkdir /tmp/dangto** to make directory dangto in /tmp then **cd /tmp/dangto** to go to the directory dangto

- **touch password** to make a file to save the password

- **touch script.sh** to make a file to save the script

- **nano script.sh** to edit the file script.sh

Then we add this to script.sh:\
`#!/bin/bash`\
`for number in {0000..9999}`\
`do`\
`echo "VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar" $number`\
`done | nc localhost 30002 | grep -v "Wrong" > password`\
`echo "Done"`\
then save\(CTRL+S) and exit\(CTRL+X). Then we **cat password** to read the file and get the password for the next level

### Password: p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

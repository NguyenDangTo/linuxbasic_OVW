### A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

- **ls -l /etc/cron.d/** to list the files in the directory /etc/cron.d/. We get the result: cronjob_bandit22.

- **cat /etc/cron.d/cronjob_bandit23** to read the file cronjob_bandit22. We get the result: \
   `@reboot bandit23 /usr/bin/cronjob_bandit23.sh &> /dev/null`\
   `***** bandit23 /usr/bin/cronjob_bandit23.sh &> /dev/null` \
  So, the program is running automatically /usr/bin/cronjob_bandit22.sh
  because we have \*\*\*\*\* in the second line.

- **cat /usr/bin/cronjob_bandit23.sh** to read the file /usr/bin/cronjob_bandit22.sh. We get the result: \
  `#!/bin/bash`\
  `myname=$(whoami)`\
  `mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)`\
  `echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"`\
  `cat /etc/bandit_pass/$myname > /tmp/$mytarget`\

It means. Get variable myname by cmd: `whoami` and we get bandit23.
Get variable mytarget by cmd: `echo I am user $myname | md5sum | cut -d ' ' -f 1` and we get the text `8ca319486bfbbc3663ea0fbe81326349`.
After that, copy password from /etc/bandit_pass/bandit23 to /tmp/8ca319486bfbbc3663ea0fbe81326349.

- **cat /tmp/8ca319486bfbbc3663ea0fbe81326349** to read the file and get the password for the next level

### Password: QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G

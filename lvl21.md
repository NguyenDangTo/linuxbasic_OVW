### A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

- **ls -l /etc/cron.d/** to list the files in the directory /etc/cron.d/. We get the result: cronjob_bandit22.

- **cat /etc/cron.d/cronjob_bandit22** to read the file cronjob_bandit22. We get the result: \
   `@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null`\
   `** *** bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null` \
  So, the program is running automatically /usr/bin/cronjob_bandit22.sh
  because we have **\*** in the second line.

- **cat /usr/bin/cronjob_bandit22.sh** to read the file /usr/bin/cronjob_bandit22.sh. We get the result: \
  `#!/bin/bash`\
  `chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv`\
  `cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv`\

-**cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv** to read the file and get the password for the next level

### Password: WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff

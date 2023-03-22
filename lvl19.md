### To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

- **file bandit20-do"** to check type of file bandit20-do. We get the result: setuid ELF 32-bit LSB executable. So, it is a setuid binary.
  To run a setuid ELF 32-bit LSB executable file. We need to use **./bandit20-do**

- **./bandit20-do cat /etc/bandit_pass/bandit20"** to get the password for the next level.

### Password: VxCazJaVykI6W36BkBU0mJTCM8rR95XT

### The password for the next level is stored somewhere on the server and has all of the following properties: owned by user bandit7, owned by group bandit6 ,33 bytes in size

- **find / -group bandit6 -user bandit7 -size 33c** to find the file with
  owned by user bandit7
  owned by group bandit6
  33 bytes in size.

we get /var/lib/dpkg/info/bandit7.password

- **cat /var/lib/dpkg/info/bandit7.password** to read the content of the file.

### Password: z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

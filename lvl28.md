### There is a git repository at ssh://bandit28-git@localhost/home/bandit28-git/repo. The password for the user bandit28-git is the same as for the user bandit28. Clone the repository and find the password for the next level.

- **mktemp -d** to make a temporary directory then **cd** to go to the directory

- **git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo** to clone the repository.

- **cd repo** to go to the directory repo

- **ls -la** to list all directories. We got the file `README`

- **cat README.md** to read the file README then we get:\
   `# Bandit Notes`\
   `Some notes for level29 of bandit.`\
   `## credentials`\
   `- username: bandit29`\
   `- password: xxxxxxxxxx`\
  we do not have the password for the next level. Maybe someone had commit to change the password for the next level. So we need to find the commit to get the password.

- **git log** to list all commits. We see a commit to fix leak password. So, to show the diffence before commit we use **git diff 104db85a904e9691ff22aafe1a96124c88f75afa^!**.
  we see:\
   `-- password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S`\
   `+- password: xxxxxxxxxx`\
  we get the password for the next level.

### Password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S

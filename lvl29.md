### There is a git repository at ssh://bandit29-git@localhost/home/bandit29-git/repo. The password for the user bandit29-git is the same as for the user bandit29. Clone the repository and find the password for the next level.

- **mktemp -d** to make a temporary directory then **cd** to go to the directory

- **git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo** to clone the repository.

- **cd repo** to go to the directory repo

- **ls -la** to list all directories. We got the file `README` and we get:\
  `# Bandit Notes`\
   `Some notes for level30 of bandit.`\
   `## credentials`\
   `- username: bandit30`\
   `- password: <no passwords in production!>`\

- **git log** to list all commits. We get nothing so we need to check do we in the right branch by **git branch -a**. We are in the branch **master**. So we need to check the branch **dev**. We use **git checkout dev** to go to the branch **dev**. Then we use **git log** to list all commits. We see a commit to fix leak password. So, to show the diffence before commit we use **git diff fbbce0ec6c80acb0fdc00ebb4b5228dd868fd799^!**.
  we see:\
   `-- password: <no passwords in production!>`\
   `+- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS`\
  we get the password for the next level.

### Password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

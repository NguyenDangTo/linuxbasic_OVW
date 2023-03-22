### There is a git repository at ssh://bandit30-git@localhost/home/bandit30-git/repo. The password for the user bandit30-git is the same as for the user bandit30. Clone the repository and find the password for the next level.

- **mktemp -d** to make a temporary directory then **cd** to go to the directory

- **git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo** to clone the repository.

- **cd repo** to go to the directory repo

- **ls -la** to list all directories. We got the file `README` and we get:\
   `just an epmty file... muahaha`\
   so we need to go `.git` to find a hint by **cd .git**.
  then we use **ls -a** to see all directories. We get:\
   `.`\
   `..`\
   `branches`\
   `config`\
   `description`\
   `HEAD`\
   `hooks`\
   `info`\
   `objects`\
   `packed-refs`\
   `refs`\
- **cat packed-refs** to read the packed-refs.
  we get:\
  `# pack-refs with: peeled fully-peeled sorted`\
   `cf552c166d78421e64ddf52f850e680075d216e1 refs/remotes/origin/master`\
   `831aac2e2341f009e40e46392a4f5dd318483019 refs/tags/secret`\
   so we get the tags/secret. So we need to back to the directory repo and use **git show secret** to show the tag and get the password for the next level.

### Password: OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt

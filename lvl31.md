### There is a git repository at ssh://bandit31-git@localhost/home/bandit31-git/repo. The password for the user bandit31-git is the same as for the user bandit31. Clone the repository and find the password for the next level.

- **mktemp -d** to make a temporary directory then **cd** to go to the directory

- **git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo** to clone the repository.

- **cd repo** to go to the directory repo

- **ls -la** to list all directories. We got the file `README` and we get:\
   `This time your task is to push a file to the remote repository.`\
   `Details:`\
   `File name: key.txt`\
   `Content: 'May I come in?'`\
   `Branch: master`\

- **echo 'May I come in?' > key.txt** to create the file `key.txt` and add the content to the file.
- **git add key.txt** to add the file to the staging area.
- **git commit -m "Add key.txt"** to commit the file to the repository.
- **git push origin master** to push the file to the remote repository.
- **ls -la** to list all directories. We got the file `README` and we get the password for the next level.

### Password: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y

# Git command

#### How to create user in git 
  ```sh
Copy
  ```
```sh
git config  - -global user.name “swapon”
git config  - -global user.email mydev911@gmail.com
To check 
git config --list

  ```
  #### Create file 
  ```sh
touch file1.txt
git status
git init 

  ```
  
#### untrack file to track . how to track untrack file
  ```sh
git add file1.txt
  ```
```sh
#### multiple file to track
git add .
  ```
#### upload file to git repository 
  ```sh
git commit -m "intial commit"
  ``` 
#### if we write on file1 
  ```sh
1. we need to stage and then commit
git add file1
# stage all commit 
git add .

## commit
git commit -m "text added"
## push to remote repository
git remote add origin https://github.com/mydev911/Git-Command.git
git push -u origin master

  ```
```sh  

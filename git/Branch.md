![Group 2](https://user-images.githubusercontent.com/23219981/190289696-68c0695a-0ae0-4bd7-8fe9-bb2761d094cf.jpg)
# Branch
https://devconnected.com/create-git-branch/#:~:text=The%20easiest%20way%20to%20create,branch%20you%20want%20to%20create.&text=To%20achieve%20that%2C%20you%20will,feature%E2%80%9D%20as%20the%20branch%20name.
#Create 4 file and add this file to stage and commit to local
  ```
touch file1.txt
git add file1.txt
or 
git add .

git commit -m "commit"

```
#### To check log  and hash
```
git log
git log --oneline
```
### To create branch
we need hash value
```
git checkout -b <branch-name>
git branch feature1 HASH-VALUE-1
```
### Check branch
```
git branch
```
#### Go inside the branch
```
git checkout BRANCH-NAME
```
##### EXAMPLE
```
# git branch create a file
touch file100.txt
git add .
git commit -m "file100.txt file add"
# push remote repository
git push -u origin BRANCH_NAME

```

# basic \
create a git repo
---
```
git init
```

add trace
---
```
git add [filename]
#git add .        #add trace to all file
```

stop trace
---
```
git rm --cached [filename]
```

commit source code
---
```
git commit -m "discription"
#git commit -a
```

check changes
---
```
git diff
```

check status
---
```
git status
```
# branch \
add branch
---
```
git branch [branch name]
```

switch to particular branch
---
```
git checkout [branch name]
```

merge branch to master
---
```
git merge [branch name]
```

remove a branch
---
```
git branch -d [branch name]
#git branch -D [branch name]     #force to delete even if there are works not stored
```

# remote \
add usl
---
```
git remote add origin [url]
```

upload
---
```
git push --set-upstream origin master
#git push --set-upstream origin [branch name]
```

sync repo
---
```
git pull
```

clone repo
---
```
git clone [url]
```

auto remind password&username
---
```
git config credential.helper store
```

# config \
```
#config username
git config --global user.name "[username]"
#config email
git config --global user.email "[email]"
#config editor
git config --global core.editor "[editor]"
```

### Installing prerequisites

### Updating upstream

First time:
```
 git remote add upstream git@github.com:coursera-dl/coursera-dl.git
 git checkout -b master origin/master
```

Other times:
```
 git checkout master
```
 
 Then, all times:
 ```
 git fetch --all
 git merge upstream/master
 git push origin master
 git checkout f-master
 git rebase master
 git push origin f-master --force
```

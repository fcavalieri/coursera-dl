### Installing prerequisites in PyCharm

```
File -> Settings -> Project: coursera-dl -> Python Interpreter  -> Add new conda environment
Terminal Tab -> conda install --file requirements.txt
```

### Common usage
In browser logoff from Coursera. Login again. In the Chrome developer pane, look in Application -> Storage -> Cookies -> https://api.coursera.org
and copy the value of the CAUTH cookie. Use NO QUOTES in what follows.

Listing enrolled courses:
```
--list-courses -ca G8I ... 91g --debug
```

Downloading a course (no notebooks!):
```
--path D:\Courses machine-learning --jobs 4 -ca G8I ... 91g
```

Downloading the notebooks of a course:

1) Launch one of your notebooks from coursera.org
2) In the upper left, click the Coursera logo
3) You'll see a file view page that lists all Jupyter resources in your current course. Click the New, then select Terminal to open the system command line.
4) You'll see a shell prompt open. In the shell prompt, type or paste the following statements:
5) Run: `rm -f ~/workspace.tar.gz && rm  -f ~/work/workspace.tar.gz && tar -czf ~/workspace.tar.gz ~/work && mv ~/workspace.tar.gz ~/work/workspace.tar.gz`
6) Once the commands run successfully, click on the ‘Coursera’ logo again to return to the file view.
7) In the file view, select workspace.tar.gz, then click Download. Your browser will download the workspace archive, which is yours to keep.
Remove the archive file: rm ~/work/workspace.tar.gz*
Note: If your zip file is larger than 100MB, you will need to split it up into smaller files instead and download each of them, using the following commands:

tar -czf - ~/work | split --bytes=100MB - ~/workspaces.tar.gz

mv ~/workspace.tar.gz* ~/work/

Source: https://learner.coursera.help/hc/en-us/articles/360004990332


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


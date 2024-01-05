Add all files (.) to git:
```shell
git add . 
```


Commit your git changes with a message
```shell
git commit -m "message" 
```

Push your git changes to branch "main" on remote "origin" 
```shell
git push origin main
```

## Try it yourself

Create a new directory:
```shell
mkdir learningGit
```

Initialise a git repository
```shell
git init
```

Save "my first repo" to a file "readme.txt"
```shell
echo "my first repo" > README.txt
```

Tell git to track all the files in the repo
```shell
git add . 
```

Commit the changes (store a record of the repo at this point)
```shell
git commit -m "I'm learning git!" 
```

Go to github and create a new repository (can be private)
Tell your local git where to push files to. Copy (from github) and execute (locally) the line that looks like: 
```shell
git remote add origin https://github.com/AlexisBallo2/learningGitRepo1.git
```

Now we can push our files to github
```shell
git push origin main
```

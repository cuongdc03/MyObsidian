To Create a new Local Repository :
```console
$ git init
```

This creates a new subdirectory named `.git` that contains all of your necessary repository files — a [[git]] skeleton. At this point, nothing in your project is tracked yet.
If you want to start version-controlling existing files (as opposed to an empty directory), you should probably begin tracking those files and do an initial commit. You can accomplish that with a few `git add` commands that specify the files you want to track, followed by a 
[[git commit]]
```console
$ git add *.c
$ git add LICENSE
$ git commit -m 'Initial project version'
```
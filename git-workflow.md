# BigContainer git work-flow

The only rule of thumb: **Anything in the master branch is deployable**

## Workflow example

To work on some new feature/bugfix create a descriptively named branch off of master.

1. Create your working branch and jump to it

   On this branch I'm going to work with flume templates, so I've named it "flume-service"

   ```
   $ git checkout -b flume-service

   # This is shorthand for:
   #  git branch flume-service
   #  git checkout flume-service
   ```

2. Push your brand new branch to the remote server:

   ```
   $ git push -u origin flume-service
   ```

3. Push your commits to your named branches on the server constantly. Since the
  only thing we really have to worry about is master from a deployment
  standpoint, pushing to the server doesn’t mess anyone up or confuse things.

4. When you need feedback or help, or you think the branch is ready for merging,
  open a pull request.

5. If master branch has changes and you want work with this updates changes in
  your working branch you can merget the changes FROM master to your working branch:

```
$ git checkout flume-service
$ git merge master
```

## Tips

* Check diffs before commit within the $EDITOR
```
$ git commit -v
```

References:
* GitHub workflow: https://help.github.com/articles/what-is-a-good-git-workflow/
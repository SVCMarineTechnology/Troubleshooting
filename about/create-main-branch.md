# Create Main Branch

At this point our repo doesn't have any [branches](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-branches), including `main`. We can create one by making our first commit and pushing it. Complete the following procedure to do so.

## Create Main Branch

1. Open a [Troubleshooting](https://github.com/SVCMarineTechnology/Troubleshooting) command prompt

2. Execute the following     commands:

   ```
   git init
   git checkout -b main
   	
   echo "TBD" >> README.md
   git add .
   git commit -m "initial commit"
   git remote add origin https://github.com/SVCMarineTechnology/Troubleshooting
   git push -u origin main
   ```

We're doing a couple of things here.  First `git init` turns a plain directory into a git repository (generating the files required to do so).  The remaining commands create a `README.md` file (with `TBD` as the content), creates a commit with the new file, and pushes it to the `main` branch in the repo.  This effectively creates the `main` branch.

For additional information see:<br>[git init](https://github.com/git-guides/git-init)

[git commit](https://github.com/git-guides/git-commit)

[Pushing commits to a remote repository](https://docs.github.com/en/get-started/using-git/pushing-commits-to-a-remote-repository)

## Next Steps

Now that we've created `main` we can [configure branch settings](configure-branch-settings.md) for the new branch.
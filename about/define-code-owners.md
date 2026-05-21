# Define Code Owners

The [branch rule we setup earlier](configure-branch-settings.md) includes the `Require review from Code Owners` option.  In order for this to work we need to define the code owners by creating a [CODEOWNERS](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners) file.  Complete the following procedure to do so.

## Create a new Branch

1. Open a [Troubleshooting](https://github.com/SVCMarineTechnology/Troubleshooting) command prompt
2. Create a new branch.  

## Add CODEOWNERS File

1. create a new file named `CODEOWNERS` at the root of the repo with the following content:

   ```yaml
   # CODEOWNERS reference:
   #   https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners
   
   # These owners will be the default owners for everything in
   # the repo. Unless a later match takes precedence,
   # review when someone opens a pull request.
   *       @MichelBarnett @beemersboat
   ```

> [!TIP]
>
> This file includes two users (collaborators) in the repo.  You can add as many as you like.

## Create and Merge PR

1. Create a PR from your branch and merge
2. Delete the branch (locally and in the repo)

## Next Steps

With the CODEOWNERS file created, we'll proceed with some additional repo configuration.  Specifically [configuring GitHub Pages](configure-github-pages.md).
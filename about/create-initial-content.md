# Create Initial Content

At this point the repo has been configured the way we need, but we don't have the structure of our site setup yet.  The following describes the updates made to setup the site with it's current look-and-feel.  This includes:

- Setting the application logo - This is the Skallywags logo that you see in the upper left of every page on the site
- The three-menu structure you see in the current site:
  - Troubleshooting
  - How to Contribute
  - About
- Default markdown and `toc.yml` files for the three areas above.

## Create a new Branch

1. Open a [Troubleshooting](https://github.com/SVCMarineTechnology/Troubleshooting) command prompt

2. Create a new branch.  For example:

   ```powershell
   git checkout -b michelbarnett/initialDocFXStructure
   ```

## Add Initial Content

1. Modify the repo with the changes in this PR:

   [Initial DocFX configuration and menu/folder structure · Pull Request #4](https://github.com/SVCMarineTechnology/Troubleshooting/pull/4)

We won't provide a detailed walkthrough of these files here, since the changes are pretty straight-forward.

> [!IMPORTANT]
>
> There's a change that was made after this PR was merged that should have been made here.  Specifically the `metadata` array should be removed from the `docfx.json` file found at the root of the repo.  Specifically you'll note that the content below appears in the `docfx.json` file in the PR above, but it's not in the latest version of the file:
>
> ```yaml
>   "metadata": [
>     {
>       "src": [
>         {
>           "src": "../src",
>           "files": [
>             "**/*.csproj"
>           ]
>         }
>       ],
>       "dest": "api"
>     }
>   ],
> ```
>
> This is configuration for a DocFX feature that we're not using.  If you don't delete this from `docfx.json` then everything works, but you'll get a couple of extraneous warnings when you use DocFX to compiles your markdown files.

## Create and Merge PR

1. Create a PR from your branch and merge
2. Delete the branch (locally and in the repo)

## Next Steps

That's it for the repo setup.  The last thing to do is [verify the initial site](verify-initial-site.md).


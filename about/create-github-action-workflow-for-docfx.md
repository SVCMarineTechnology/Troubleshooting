# Create GitHub Action Workflow for DocFX

TBD

## Create a new Branch

1. Open a [Troubleshooting](https://github.com/SVCMarineTechnology/Troubleshooting) command prompt

2. Create a new branch

   ```powershell
   git checkout -b MichelBarnett/initdocfx
   ```

## Initialize DocFX

1. execute the following command:

   ```powershell
   docfx init -y
   ```

## Add GitHub Action Workflow

1. Create a new file in the repo named:

   `.\github\workflows\docfx.yml`

2. Add the content in this link to the file:

   [docfx.yml](https://github.com/SVCMarineTechnology/Troubleshooting/blob/d50f23969dbc4fe728d00f3f91387bc3e5427219/.github/workflows/docfx.yml)

## Create and Merge PR

1. Create a PR from your branch and merge
2. Delete the branch (locally and in the repo)

## Next Steps

That's it for the repo setup.  The last thing to do is [create the initial content](create-initial-content.md) we'll need for the site.
# Create Branch

In order to contribute changes to the repo, you'll need to create a branch to store your changes.  Complete the following procedures to do so.

## Create a Branch

1. Open a [Troubleshooting](https://github.com/SVCMarineTechnology/Troubleshooting) command prompt.

2. Pull the latest changes from main by executing

   ```powershell
   git checkout main
   git pull
   ```

   > [!TIP]
   >
   > Before creating a new branch from `main`, it's always a good idea to ensure you're on the `main` branch first, and that you have the latest changes by going a `git pull`.

3. Create a branch by executing the following:

   ```powershell
   git checkout -b <UserName>/<BranchName> 
   ```

   for example:

   ```powershell
   git checkout -b michelbarnett/contribute
   ```

   > [!NOTE]
   >
   > By convention prefix the branch with your user name and a forward slash and then choose a branch name that reflects the changes you're making.  In this example, we're creating a branch for changes to the repo contribution procedures.

## Set the Upstream Branch

Before we can push changes we need to associate the local branch we just created with a corresponding branch in the GitHub repo.  Complete the following procedure to do so.

1. In the same command prompt execute:

   ```powershell
   git push
   ```

   The response will look something like this:

   ```powershell
   fatal: The current branch michelbarnett/contribute has no upstream branch.
   To push the current branch and set the remote as upstream, use
   
       git push --set-upstream origin michelbarnett/contribute
   ```

   > [!NOTE]
   >
   > The `--set-upstream` command is what we need to execute.  Running `git push` when we know it'll fail is an easy way to get git to generate the command for us.

2. Copy-and-paste the command that git just gave us:

   ```powershell
   git push --set-upstream origin <BranchName>
   ```

   for example:

   ```powershell
   git push --set-upstream origin michelbarnett/contribute
   ```

   This associates our local branch with a remote branch in the repo (that's named the same).  

   > [!TIP]
   >
   > From now on you can push changes simply by executing:
   >
   > ````powershell
   > git push
   > ````

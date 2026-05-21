# Configure GitHub Pages

One of the key features that GitHub provides is built-in hosting for HTML content (in this case, generated from our markdown files).  So, even though the repo is found at this URL:

https://github.com/SVCMarineTechnology/Troubleshooting

there's a separate URL at which our hosted documentation can be found:

https://svcmarinetechnology.github.io/Troubleshooting/

The feature that enables this is called [GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages).  GitHub pages is a static site hosting service that takes content from our repository on GitHub, optionally runs it through a build process, and publishes a website using that content.

In our repo we use DocFX to transform our Markdown files into HTML.  So we'll configure GitHub Pages to automatically use DocFX to "build" our HTML pages from our repo everytime we merge an update to `main`.  That means the content in our web site is always up-to-date with the latest changes in our repo.

Making all of this work means 1) making a simple configuration change in the repo 2) adding a configuration file to the repo that tells GitHub pages how to transform our Markdown into HTML.  

Complete the following procedures to set this up.

> [!NOTE]
>
> GitHub Pages is available in public repositories created with the [GitHub Free](https://github.com/pricing) pricing plan (which is the plan we're using for our repro).  However, GitHub Pages is only available in private repositories with paid plans.  This is a key reason our repo is public.

## Configure GitHub Pages Source

We need to tell GitHub Pages where it gets the content that it publishes to the Internet.  One option is to refer it to a branch and folder where our static HTML resides: in this case the source is **Deploy from a branch**.  In our case we need a process to dynamically run DocFX on the Markdown files we merge into `main` and regenerate the HTML pages based on any updates.  This is accomplished by a feature called [GitHub Actions](https://docs.github.com/en/actions/get-started/understand-github-actions).  So, in our case, we need to specify the GitHub Pages source as **GitHub Actions**.  Complete the following steps to do so.

1. Open a browser to the [Troubleshooting](https://github.com/SVCMarineTechnology/Troubleshooting) repo and *login as* **SVCMarineTechnology**

2. Select **Settings**

3. In the left-hand navigation bar select **Pages**

4. In the **Build and deployment** section, set the parameters as follows:

   | Parameter | Example Value  | Comments |
   | --------- | -------------- | -------- |
   | Source    | GitHub Actions |          |

5. Click **Save**

For additional information see:<br>[Publishing with a custom GitHub Actions workflow](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-with-a-custom-github-actions-workflow)

## Create GitHub Action Workflow for DocFX

A [GitHub Action](https://docs.github.com/en/actions/get-started/understand-github-actions) is based on what GitHub calls a *workflow*.  A workflow is just a configurable automated process that runs a *job* when triggered by an *event*.  When that event occurs it executes the job which consists of a set of  steps.  Each step may be a custom command or it may use a predefined *action*.

In our case we need a workflow where the triggering event is a merge to the `main` branch.  When that event occurs we want to execute a set of actions that retrieves our Markdown files, runs them through DocFX (to generate HTML files), and then publishes that HTML to our GitHub Pages site.

In the previous procedure we told GitHub Pages that its source is GitHub Actions.  We'll configure GitHub Actions by adding a single file to our repo.  Specifically:

```powershell
.github\workflows\docfx.yml
```

GitHub actions are hard-coded to look in the `.github\workflows` folder in your repo.  GitHub looks for any yaml file in this directory.  Each one it finds is expected to be a [GitHub Action Workflow](https://docs.github.com/en/actions/concepts/workflows-and-actions/workflows) definition.  This file tells GitHub what do when it executes the workflow.  Any workflow whose `on:` block matches the triggering event is executed.  So, what we need to do is add this file with the appropriate content that will execute the steps we need.

Complete the following procedures to do so.

for additional information see:<br>[Workflows](https://docs.github.com/en/actions/concepts/workflows-and-actions/workflows)

### Create a new Branch

1. Open a [Troubleshooting](https://github.com/SVCMarineTechnology/Troubleshooting) command prompt

2. Create a new branch.  For example:

   ```powershell
   git checkout -b MichelBarnett/initdocfx
   ```

### Initialize DocFX

1. execute the following command:

   ```powershell
   docfx init -y
   ```

This command creates default DocFX files (in this case, in the root of our repo) that we'll use to transform our Markdown into HTML.  The main file this command generates is `docfx.json` file (which is the main DocFX configuration file).  There's also a default table-of-contents file (`toc.yml`) and some sample markdown files.  Any new DocFX environment would be initialized this way.

### Add GitHub Action Workflow

1. Create a new file in the repo named:

   `.github\workflows\docfx.yml`

2. Add the following content to the file:

   ```yaml
   name: DocFX Deployment
   on:
     push:
       branches: [main]
   permissions:
     contents: read
     pages: write
     id-token: write
   jobs:
     build:
       runs-on: ubuntu-latest
       steps:
         - name: Checkout
           uses: actions/checkout@v4
         - name: Setup .NET
           uses: actions/setup-dotnet@v4
           with:
             dotnet-version: 8.x
         - name: Build DocFX
           run: |
             dotnet tool update -g docfx
             docfx docfx.json
         - name: Upload artifact
           uses: actions/upload-pages-artifact@v3
           with:
             path: _site  # Default DocFX output folder
         - name: Deploy to GitHub Pages
           uses: actions/deploy-pages@v4
   ```

You don't need to understand this in any detail to know that it works (if you want additional detail see [DocFX Quick Start](https://dotnet.github.io/docfx/)).  But here are a few key parts:

The trigger can be found in these lines:

```yaml
on:
  push:
    branches: [main]
```

So this particular workflow is triggered any time there's a change pushed to the `main` branch.

There's only one job described in the file and it contains these key steps:

```yaml
steps:
      - name: Checkout
        uses: actions/checkout@v4
      . . .
      - name: Build DocFX
        run: |
          . . .
          docfx docfx.json
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: _site  # Default DocFX output folder
      - name: Deploy to GitHub Pages
        uses: actions/deploy-pages@v4
```

Each step of these steps are summarized below:

- `actions\checkout@v4` - this "checks out" our repository so that the workflow can access the files
- `run:`- The `docfx docfx.json` command transforms our Markdown into HTML and places the generated HTML files into a folder named `_site`.
- `actions/upload-pages-artifact@v3` - This packages up the files in the `_site` in preparation for deployment.
- `actions/deploy-pages@4` - This deploys the package just created to GitHub Pages.  Once deployed, the content is accessible from our GitHub pages site.

### Create and Merge PR

1. Create a PR from your branch and merge
2. Delete the branch (locally and in the repo)

## Next Steps

Everything we just configured just means:

> When a an update is made to `main` branch, start a workflow that uses DocFX to compile our Markdown files into HTML and publish that content to GitHub Pages.

Now that GitHub Pages is setup, the last thing to do is [create the initial content](create-initial-content.md) we'll need for the site.
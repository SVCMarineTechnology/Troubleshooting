# Configure GitHub Page Settings

We need to configure GitHub to use DocFX to render our documentation.  Complete the following procedure to do so.

> [!NOTE]
>
> The site must be public in order to do complete this procedure (or you'll be required to use GitHub Enterprise for a fee)

## Configure Setup Action

1. Open a browser to the [Troubleshooting](https://github.com/SVCMarineTechnology/Troubleshooting) repo and *login as* **SVCMarineTechnology**

2. Select **Settings**

3. In the left-hand navigation bar select **Pages**

4. In the **Build and deployment** section, set the parameters as follows:

   | Parameter | Example Value  | Comments |
   | --------- | -------------- | -------- |
   | Source    | GitHub Actions |          |

5. Click **Save**

For additional information see:<br>[Configuring a publishing source for your GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-with-a-custom-github-actions-workflow)

## Next Steps

The previous procedure is the first set of steps required to configure GitHub to host our content at https://svcmarinetechnology.github.io/Troubleshooting/.  The next step is to complete this configuration by [creating a GitHub Action Workflow](create-github-action-workflow-for-docfx.md).
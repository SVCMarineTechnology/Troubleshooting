# Tooling Primer

Making changes to the  [Troubleshooting](https://github.com/SVCMarineTechnology/Troubleshooting) repo requires an understanding of the following technologies:

- **Git & GitHub** - You should have a working understanding of Git and GitHub along with  how they work.  Specifically, you should be comfortable cloning a repo, creating a branch, changing files, creating a pull request (PR), participating in a review, and merging your changes.

- **Markdown** - You should be comfortable writing Markdown from scratch (even though you might use a Markdown editor).

- **DocFX** - You should understand what DocFX is and how it's configured.  At a minimum, you'll need to test your updates by running the DocFX command line and you should be comfortable modifying table-of-contents (`toc.yml`) files.  Familiarity with Markdown Extensions is also helpful.

The guidance in this repo is not designed to teach you these technologies.  But if you are new to any of them, the following should help you get started.

## Git & GitHub

**<u>What is it?</u>**

**Git** is a distributed version control system that lets you track changes to files, collaborate with others, and maintain a complete history of a project *locally* on your own machine.  

**GitHub** is a cloud-based platform that provides users tools to create, store, manage, and share  changes *globally*.  GitHub offers a variety of features and services that are key to maintaining our Troubleshooting guides.

Git and GitHub work together.  You make commits locally with Git, then **push** them to GitHub; you **pull** others’ changes from GitHub back to your machine. GitHub manages collaboration, Git manages the data.

**<u>URL</u>**

- Git - https://git-scm.com/
- GitHub - https://www.github.com

**<u>Getting Started</u>**

The best description of the *mechanics* of working with Git and GitHub can be found in this site:

- [How to Contribute](introduction.md) - The steps in the contribution procedure link to pages that provide full detail on the commands you need to execute to complete each step.  Technically, you can just follow the instructions to get your work done.  But understanding the basic concepts behind Git and GitHub will make it easier to understand *why* you're executing these commands.  

The following videos provide a brief explanation of Git and GitHub that provide context on the contribution procedures just mentioned:

- [Git vs. GitHub: What's the Difference?](https://www.youtube.com/watch?v=-Xfch1DV9Vk) - A good overview of the difference between Git and GitHub.
- [How Git Works: Explained in 4 Minutes](https://www.youtube.com/watch?v=e9lnsKot_SQ) - An explanation of the workflow you'll go through when working with Git.  This is also a good description of the key commands involved in the different stages of that workflow.

For general information you can also refer to these links:

- [Git - Reference](https://git-scm.com/docs) - A reference to all Git commands
- [GitHub Docs](https://docs.github.com/en) - General GitHub documentation

## Markdown

**<u>What is it?</u>**

Markdown is a lightweight markup language used to add formatting elements to plaintext documents using simple, human-readable symbols.

**<u>URL</u>**

- https://daringfireball.net/projects/markdown/

**<u>Getting Started</u>**

You'll likely use a Markdown tool (like [Typora](https://typora.io/)), for most of your Markdown editing.  However, it's important to understand how to write markdown from scratch (in practice, it's occasionally necessary).  The following is a good reference

- [Basic Syntax | Markdown Guide](https://www.markdownguide.org/basic-syntax/) - A concise reference for Markdown syntax.

You can also find comprehensive documentation on Markdown here:

- [Getting Started | Markdown Guide](https://www.markdownguide.org/getting-started/) - A thorough explanation of Markdown along with comprehensive learning resources on the subject.

## DocFX

**<u>What is it?</u>**

DocFX is a static documentation generator that takes .NET assemblies, XML code comments, Markdown files, and REST API specs and turns them into a full static website.

**<u>URL</u>**

- https://dotnet.github.io/docfx

**<u>Getting Started</u>**

The documentation in our repo is fundamentally Markdown.  However, there are some syntactic additions that DocFX makes that are important to know.

- [Markdown Extensions](https://dotnet.github.io/docfx/docs/markdown.html#markdown-extensions) - DocFX supports additional markdown syntax based on the extensions in the guide.  In particular, we use DocFX [Alerts](https://dotnet.github.io/docfx/docs/markdown.html#alerts) in our troubleshooting guides.
- [Table of Contents](https://dotnet.github.io/docfx/docs/table-of-contents.html) - A reference for the `toc.yml` files found in our repo.
- [Config Reference](https://dotnet.github.io/docfx/reference/docfx-json-reference.html) - Reference for the `docfx.json` file in our repo (the main configuration file for DocFX).  This file won't often change but if needed, this is the  fullreference.

Another useful resource is the command line reference for the `docfx` tool:

- [Commandline Overview](https://dotnet.github.io/docfx/reference/docfx-cli-reference/overview.html) - A full command line reference for DocFX.  This is necessary for us to run docfx locally so we can verify that our files are error free and rendering correctly.

You can also find comprehensive documentation on DocFX here:

- [Basic Concepts](https://dotnet.github.io/docfx/docs/basic-concepts.html) - Landing page for full documentation on DocFX.

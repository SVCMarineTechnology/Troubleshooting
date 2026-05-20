# Install Software on macOS

The following procedures we're run on a machine with the following software:

- TBD

You can have additional software installed but it's suggested you start with at least this version of the operating system.

Complete the following procedures in order.  When this software is installed, you'll be ready to clone the repo and edit any files that you like.

> [!IMPORTANT]
>
> The procedures in the [How to Contribute](../contribute/introduction.md) and the [About](../about/introduction.md) sections are written for Windows.  These procedures have been tested on a Mac, but you'll need to make a few adjustments:
>
> - Examples that include file directories are based on the Windows file system.  For example, the convention used in these procedures is to clone your repo to:
>
>   ``` powershell
>   \github\SVCMarineTechnology\Troubleshooting
>   ```
>
>   If you're on a Mac, it's suggested you use this same path.  But you'll need to decide where this folder is rooted.
>
> - Any references to opening a **Command Prompt** should be translated as opening **Terminal**
>
> - In the procedures in this repo, it's common to see steps that look like this:
>
>   1. Open a [Troubleshooting](https://github.com/SVCMarineTechnology/Troubleshooting) command prompt
>
>   If you see this, then what this means on a Mac is opening **Terminal** and setting the current directory to the root folder of the locally cloned  [Troubleshooting](https://github.com/SVCMarineTechnology/Troubleshooting) repo.

## Install Git

There are multiple ways to install Git.  One of easier methods is installing the Xcode command line tools (which include Git).  Complete the following steps to do so.

1. Open **Terminal** and execute:

   ```powershell
   xcode-select --install
   ```

   you should see something like this:

   ![]()

Now when you open Terminal, you can execute `git` by typing:

```powershell
git
```

For additional information see:<br>[Git - Install for macOS](https://git-scm.com/install/mac)

## Install DocFX

1. Install the latest version of the .NET SDK by opening this link and following the directions:

    [Browse all .NET versions to download](https://dotnet.microsoft.com/en-us/download/dotnet)

2. Open a **Terminal** and execute:

   ```powershell
   dotnet tool update -g docfx
   ```

   you should see something like this:

   ![]()

3. Install the latest version of Node.js by opening this link and following the directions:

   [Node.js — Run JavaScript Everywhere](https://nodejs.org/en)

Now when you open a command prompt you can execute `docfx` by typing:

```powershell
docfx
```

For additional information see:<br>[DocFX Quick Start](https://dotnet.github.io/docfx/)

[Install .NET on macOS - .NET](https://learn.microsoft.com/en-us/dotnet/core/install/macos#install-net)

## [Optional] Install Visual Studio Code

1. Install the latest version of Visual Studio Code by opening this link and following the directions:

   [Download Visual Studio Code - Mac, Linux, Windows](https://code.visualstudio.com/download)

For additional information see:<br>[Visual Studio Code](https://code.visualstudio.com/)

## [OPTIONAL] Install Typora

1. Install the latest version of Typora by opening this link and then downloading and installing the tool for your platform:

   [Typora — simple yet powerful Markdown reader.](https://typora.io/)

   > [!TIP]
   >
   > The download link is near the bottom of the page.

2. Purchase a license using the same link above (the purchase button is right next to the download button).
3. Enter the license key that's emailed to you into Typora (you'll be prompted at initial startup)

For additional information see:<br>[Typora — simple yet powerful Markdown reader.](https://typora.io/)
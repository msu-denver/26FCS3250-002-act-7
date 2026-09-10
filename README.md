# Overview

In this activity, you will set up GitHub CLI so that you can run GitHub commands from your terminal.

# Setup

The easiest way to install the GitHub CLI (gh) on macOS is with Homebrew. GitHub officially recommends this method. Run the following command to check if you have Homebrew: 

```
brew --version
```

If the command is not found, install Homebrew:

```
/bin/bash -c "$(curl -fsSL 
https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Install GitHub CLI using: 

```
brew install gh 
```

On Windows, the easiest method is WinGet (the Windows Package Manager). GitHub CLI is available as the package GitHub.cli.

```
winget install --id GitHub.cli --exact
```

You can also download the Windows installer (MSI) from the GitHub CLI releases page and run it like any other Windows application. GitHub provides MSI installers for x64, x86, and ARM64 Windows systems.

To verify the installation, run: 

```
gh --version
```

To authenticate on GitHub run: 

```
gh auth login
```

Follow the steps for the authentication. To check if authentication was successful, run: 

```
gh auth status 
```

# Instructions

Run the GitHub commands using gh. 

## List Repos

```
gh repo list
```

## Create a Repo

```
gh repo create act-7 --public
```

## Create a Pull Request 

Before running the command below, create the ```feature/<YOUR_NAME>``` branch, stage a file, commit and push your changes. Replace ```<YOUR_NAME>``` with your name. For example, I would use ```feature/thyago-mota``` for my branch name. 

```
gh pr create --base main --head feature/<YOUR_NAME> --title "Add bla-bla feature by <YOUR_NAME>" --body "My first pull request..."
```  

## List Pull Requests 

```
gh pr list
```

Make sure your pull request appears in the output of gh pr list.
Activity 7 completed by Yasemin

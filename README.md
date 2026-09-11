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

Run GitHub basic commands using gh. 

* List Repos: **gh repo list**
* Create a new public Repo: **gh repo create act-7 --public**

Now work on these two typical scenarios. 

## Scenario 1: Team Collaboration

Work with a classmate. Throughout this activity, the two students will be referred to as Joe and Sam.

Joe creates a new GitHub repo, referred to as https://github.com/joe/repo. Joe clones their repo locally, adds a README.md file, commits and pushes the changes to the remote. 

Joe then protects protects the main branch using a branch protection rule (or ruleset, depending on the GitHub interface) and adds Sam as a collaborator with write access. 

Sam clones the repo and creates a new feature branch called **feature/sam**, adds a file to it, and commits the changes. Sam then pushes the feature branch to the remote using: 

```
git push origin feature/sam
```

Sam then creates a pull request so the new feature can eventually be merged into the remote main branch. 

```
gh pr create --base main --head feature/sam --title "Bla-bla" --body "Bla-bla..."
```

Joe reviews the pull request and authorize the merge to main using the GitHub web interface. 

## Scenario 2: Open Source Collaboration

Joe creates a new GitHub repo, referred to as https://github.com/joe/repo. Joe clones their repo locally, adds a README.md file, commits and pushes the changes to the remote. 

Joe then protects protects the main branch using a branch protection rule (or ruleset, depending on the GitHub interface). Joe does NOT add Sam as a collaborator. 

Instead, Sam forks Joe's repository using the GitHub web interface. This creates a copy of the repository under Sam's GitHub account. Sam clones the forked repository locally and creates a new feature branch called **feature/sam**. Sam adds a file, commits the changes, and pushes the feature branch to their fork:

```
git push origin feature/sam
```

Sam then creates a pull request from the fork's **feature/sam** branch to Joe's main branch:

```
gh pr create --repo joe/repo --base main --head sam:feature/sam --title "Bla-bla" --body "Bla-bla..."
```

Joe reviews the pull request and authorize the merge to main using the GitHub web interface. 

That's it!

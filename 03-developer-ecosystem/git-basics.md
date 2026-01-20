# Git Basics for Technical Writers

As a technical writer, you often collaborate on documentation, manage versions of content, and integrate your work into larger projects. Git is a powerful version control system that helps you track changes, collaborate with teams, and maintain a history of your documents. This guide provides a foundational understanding of Git, tailored for technical writers who may not be deeply technical but need to use it effectively for documentation workflows.

## What is Git?

Git is a distributed version control system (VCS) created by Linus Torvalds in 2005 for managing Linux kernel development. Unlike centralized systems (e.g., SVN), Git allows every user to have a full copy of the repository on their local machine, enabling offline work and faster operations.

Git if useful for technical writers because of the following reasons:

- **Version Control:** Track changes to documents over time. If you make a mistake in a Markdown file or API reference, you can revert to a previous version.

- **Collaboration:** Work with developers, Product Managers and other writers without overwriting each other's changes.

- **Integration with Tools:** Git powers platforms like GitHub, GitLab, or Bitbucket, where you can host documentation repos, use issues for feedback, and automate builds. For example, with the CI/CD for generating docs with tools like Sphinx or MkDocs.

Git is free, open-source, and runs on Windows, macOS, and Linux.

## Key Concepts in Git

Before diving into commands, understand the following core ideas:

- **Repository (Repo)**: A folder containing your project files and their history. It can be local (on your machine) or remote (on a server like GitHub).

- **Commit**: A snapshot of your changes at a specific point. Each commit has a unique ID (hash), a message describing the change, and metadata like author and timestamp.

- **Branch**: A parallel line of development. The default branch is often called main (formerly master). Branches let you work on features or fixes without affecting the main codebase.

- **Merge**: Combining changes from one branch into another. This is how you integrate your work.

- **Remote**: A version of your repo hosted elsewhere (e.g., GitHub). You "push" changes to the remote and "pull" from it.

- **Staging Area**: A temporary space where you prepare files for a commit using git add.

- **Clone**: Copying a remote repo to your local machine.

- **Pull Request (PR)**: On platforms like GitHub, a way to propose changes from your branch to the main repo. It's not a core Git feature but a platform-specific tool for review.

## Setting Up Git

Follow the steps to set up your Git environment.

**Step 1: Installation.** Download the installer from git-scm.com for your OS. On macOS, use Homebrew: `brew install git`. On Linux (Ubuntu/Debian), use: `sudo apt install git`. For Windows, the installer includes Git Bash, a command-line interface. Verify installation by running `git --version` in your terminal—it should display the Git version number.

**Step 2: Configuration.** Set global defaults for your identity (used in commit metadata) and editor. Run these commands:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
git config --global core.editor "nano"  # Or "vim", "code --wait" for VS Code, etc.
```

**Step 3: Authentication.** For platforms like GitHub, set up SSH for secure, passwordless access (recommended) or use HTTPS with a personal access token. Generate an SSH key with `ssh-keygen -t ed25519 -C "your.email@example.com"`, then add the public key (`~/.ssh/id_ed25519.pub`) to your GitHub account settings. Test with `ssh -T git@github.com`. For HTTPS, create a token in GitHub settings and use it when prompted. Refer to GitHub's official guide: docs.github.com/en/authentication. If using a GUI like GitHub Desktop, it handles much of this automatically.

## Basic Git Workflow for Technical Writers

Follow the steps for manage documentation workflow with the Git.

## Best Practices for Technical Writers

## Common Pitfalls and Tips

## Resources for Further Learning

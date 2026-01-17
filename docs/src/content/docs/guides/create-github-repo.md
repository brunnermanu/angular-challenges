---
title: Create a GitHub Repository from Local Project
description: Guide on how to push an existing local project to GitHub and create a new repository
contributors:
  - tomalaforge
sidebar:
  order: 8
---

This guide explains how to push an existing local project to GitHub and create a new repository.

## Prerequisites

- A [GitHub account](https://github.com/signup)
- Git installed on your local machine
- An existing project on your local machine

## Step 1: Create a New Repository on GitHub

1. Log in to your [GitHub account](https://github.com)
2. Click the **+** icon in the top right corner
3. Select **New repository**
4. Fill in the repository details:
   - **Repository name**: Choose a meaningful name for your project
   - **Description** (optional): Add a brief description of your project
   - **Public or Private**: Choose the visibility of your repository
   - **Do NOT** initialize with README, .gitignore, or license (since you already have a local project)
5. Click **Create repository**

GitHub will display instructions for pushing an existing repository. Keep this page open for reference.

## Step 2: Initialize Git in Your Local Project (if not already done)

If your project doesn't have Git initialized yet, open a terminal in your project directory and run:

```bash
git init
```

This creates a new Git repository in your project folder.

## Step 3: Add Your Files to Git

Add all your project files to the Git staging area:

```bash
git add .
```

:::tip
You can create a `.gitignore` file to exclude files you don't want to track (like `node_modules`, build artifacts, etc.).
:::

## Step 4: Create Your First Commit

Commit your files with a meaningful message:

```bash
git commit -m "Initial commit"
```

## Step 5: Connect to the Remote GitHub Repository

Link your local repository to the GitHub repository you created in Step 1. Replace `[YOUR_USERNAME]` and `[REPOSITORY_NAME]` with your actual values:

```bash
git remote add origin https://github.com/[YOUR_USERNAME]/[REPOSITORY_NAME].git
```

:::note
You can find this exact command on the GitHub page that appeared after creating your repository.
:::

## Step 6: Push Your Code to GitHub

Push your local commits to GitHub:

```bash
git branch -M main
git push -u origin main
```

The `-M` flag renames your current branch to `main`, and the `-u` flag sets up tracking so future pushes can be done with just `git push`.

## Step 7: Verify Your Repository

Go back to your GitHub repository page and refresh it. You should now see all your project files uploaded to GitHub.

## Next Steps

Now that your project is on GitHub, you can:

- Collaborate with others by inviting them as collaborators
- Create branches for new features
- Open issues to track bugs and enhancements
- Set up continuous integration/deployment
- Share your project with the world

## Troubleshooting

<details>
  <summary>Authentication Error when Pushing</summary>
  
  If you get an authentication error, you may need to:
  - Use a [Personal Access Token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) instead of your password
  - Set up [SSH keys](https://docs.github.com/en/authentication/connecting-to-github-with-ssh) for authentication
  
</details>

<details>
  <summary>Remote Already Exists Error</summary>
  
  If you see "remote origin already exists", you can either:
  - Remove the existing remote: `git remote remove origin`
  - Or update it: `git remote set-url origin https://github.com/[YOUR_USERNAME]/[REPOSITORY_NAME].git`
  
</details>

<details>
  <summary>Branch Name Conflicts</summary>
  
  If your default branch is named `master` instead of `main`, you can either:
  - Push to master: `git push -u origin master`
  - Or rename your branch: `git branch -M main` before pushing
  
</details>

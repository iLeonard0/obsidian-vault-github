# How to Set Up an Obsidian Vault with GitHub

This guide explains how to configure your Obsidian vault with a GitHub repository, allowing you to access and sync your notes across multiple devices.

---
# Initializing Repository and creating Obsidian Vault

## 1. Setting Up the Environment

### 1.1 Download Obsidian

- Go to the official Obsidian website: [Obsidian](https://obsidian.md)  
- Follow the installation instructions for your operating system.  
- Once installed, launch the app.

### 1.2 Creating a Vault

- After opening Obsidian, create a new vault by following the on-screen instructions.  
- The process is quick and straightforward: you just need to name your vault and choose a location on your device.  

---

## 2. Setting Up GitHub

### 2.1 Create or Fork a Repository

- Create a new repository on GitHub, or fork an existing `.md` repository that you want to use with your vault.

### 2.2 Install Git

- Download and install Git if you haven’t already: [Git](https://git-scm.com/install)

### 2.3 Generate a Personal Access Token (PAT)

A personal access token is required to authenticate Git with GitHub.

#### Steps to Generate a Token

1. Go to your GitHub **Profile Settings**.  
2. Navigate to **Developer Settings**.  
3. Select **Personal Access Tokens** → **Tokens (Classic)**.  
4. Click **Generate new token (classic)**.  
5. Give your token a descriptive name.  
6. Set **Expiration** to `No expiration`.  
7. Select all permissions under the **repo** scope.  
8. Click **Generate Token**.  
9. Copy the token and save it securely.

<img width="1232" height="1247" alt="GitHub Personal Access Token" src="https://github.com/user-attachments/assets/64b19b59-fb2b-4ab4-b7f5-f03f93b7b4eb" />

---

## 3. Linking Obsidian Vault with GitHub

### 3.1 Install Git Plugin in Obsidian

1. Open your Obsidian vault.  
2. Go to **Settings → Community Plugins**.  
3. If **Community Plugins** are not activated, enable them.  
4. Click **Browse** and search for `Git`.  
5. Install and enable the Git plugin.

### 3.2 Initialize Git in Your Vault

1. Open a terminal and navigate to your vault folder.  
2. Run the following commands step by step:

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://<PERSONAL_ACCESS_TOKEN>@github.com/<USERNAME>/<REPO>.git
git push --set-upstream origin main
```

Example URL format with token:
https://ghp_XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX@github.com/test/test-obsidian-vault-md.git

### 3.3 Working with Your Vault

- After linking your vault, you can make changes to your notes locally.
- To commit and sync changes to GitHub:
  1. Open the Command Palette (CMD/Ctrl + P).
  2. Type Commit-and-sync and press Enter.
  3. All edited files will be automatically pushed to your GitHub repository.

# 4. Cloning a Repository on Other Devices

To access your existing vault on a different device:

1. Create a new vault in Obsidian.  
2. Install the Git plugin as described above.  
3. Open the Command Palette (CMD/Ctrl + P).  
4. Type `Clone an existing remote repo` and press Enter.  
5. Enter your repository URL in the format:  
   `https://<PERSONAL_ACCESS_TOKEN>@github.com/<USERNAME>/<REPO_TO_CLONE>.git`  
6. Type the main branch name (usually `main`) and press Enter twice.  
7. Your repository will be cloned into the new vault.  
8. You can now make changes, commit, and sync as usual.

### Optional Settings

- Go to **Settings → Git** to enable **Pull on Startup**.  
- You can also configure **Auto Commit-and-Sync Interval (minutes)** to automate syncing changes.

---

With this setup, your Obsidian vault will be fully integrated with GitHub, allowing seamless access and synchronization across all your devices.

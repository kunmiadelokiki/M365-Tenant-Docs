# How to Push This to GitHub (Beginner Guide)

This walks you through getting the M365-Tenant-Docs folder onto GitHub for the first time.

---

## Step 1: Create a GitHub account (skip if you already have one)

1. Go to https://github.com and click **Sign up**
2. Follow the prompts to create your account
3. Verify your email address

## Step 2: Install Git on your computer

**Windows:**
- Download from https://git-scm.com/download/win
- Run the installer and accept the defaults

**Mac:**
- Open Terminal and run: `git --version`
- If not installed, it will prompt you to install Xcode Command Line Tools

After installing, open a terminal (Command Prompt, PowerShell, or Terminal on Mac) and set your identity:

```
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

## Step 3: Create a new repository on GitHub

1. Go to https://github.com/new
2. Fill in:
   - **Repository name:** `M365-Tenant-Docs`
   - **Description:** `Microsoft 365 Tenant Configuration Documentation`
   - **Visibility:** Private (recommended for confidential configs)
   - Do NOT tick "Add a README file" (we already have one)
3. Click **Create repository**
4. GitHub will show you a page with setup instructions — keep this page open

## Step 4: Push your files to GitHub

Open a terminal, navigate to the M365-Tenant-Docs folder, and run these commands one by one:

```bash
cd path/to/M365-Tenant-Docs

git init

git add .

git commit -m "Initial commit: M365 tenant configuration documentation"

git branch -M main

git remote add origin https://github.com/YOUR-USERNAME/M365-Tenant-Docs.git

git push -u origin main
```

Replace `YOUR-USERNAME` with your actual GitHub username and `path/to/M365-Tenant-Docs` with the actual path to the folder on your computer.

When you run the push command, GitHub will ask you to sign in. If prompted for a password, you will need to use a **Personal Access Token** instead (see next step).

## Step 5: Create a Personal Access Token (if needed)

GitHub no longer accepts passwords for Git operations. You need a token:

1. Go to https://github.com/settings/tokens
2. Click **Generate new token (classic)**
3. Give it a name like "Git access"
4. Tick the **repo** scope
5. Click **Generate token**
6. Copy the token — use this as your password when Git asks

## Done!

After pushing, visit `https://github.com/YOUR-USERNAME/M365-Tenant-Docs` to see your docs live on GitHub. The README will display automatically on the front page.

---

## Updating docs in the future

Whenever you update the documentation, run:

```bash
cd path/to/M365-Tenant-Docs
git add .
git commit -m "Update: describe what changed"
git push
```

This pushes your latest changes to GitHub.

## The project to import PhD codes hosted on `gitlab`

### Step 1: Create a "Group" (Organization) on GitHub
GitHub does not call them groups; it calls them Organizations. You can create a free organization attached to your personal account:
 1. Log into your personal account on GitHub.
 2. In the top-right corner, click your profile picture and select Your organizations.
 3. Click the New organization button.
 4. Choose the Free plan (this allows unlimited public and private repositories).
 5. Name your organization (e.g., my-institutional-archive), provide your email, and click Create.

### Step 2: Create Empty Repositories inside the Group
Before pushing code, GitHub requires the target repository to already exist.
 1. Go to your newly created GitHub Organization page.
 2. Click New repository.
 3. Give it the exact same name as your GitLab repository (e.g., repo1).
 4. Set the visibility to Public or Private based on your needs.
 5. CRITICAL: Do NOT initialize it with a README, .gitignore, or license. Leave it completely empty.

### Step 3: Mirror the Code via Terminal
This command-line approach copies all branches, tags, and commits exactly as they are. Repeat these commands for each repository you want to transfer:
```bash
# 1. Pull down a complete "mirror" clone from your institutional GitLab
git clone --mirror https://your-institution.edu

# 2. Enter the newly created mirror directory
cd repo1.git

# 3. Push the entire history directly into your GitHub organization repo
git push --mirror https://github.com

# 4. Clean up the temporary folder from your computer
cd ..
rm -rf repo1.git
```
Use code with caution.
(Note: If you use SSH keys, replace the https://... links with the respective git@github.com:... or git@gitlab... SSH URLs).

[reference](https://share.google/aimode/L40ydKEW21VAg6ppr)

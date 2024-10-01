# Git Tutorial: Setting Up, Working with Branches, and Merging

This tutorial will guide you through the essential steps for working with Git, from setting your username and email, to working with branches, and finally merging changes.

---

## Step 1: Setting Up Your Git Username and Email

The first step in configuring Git is setting your username and email. These will be used in each of your commits.

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

---

## Step 2: Generating an SSH Key and Adding It to GitHub

SSH keys allow you to authenticate securely with GitHub.

1. **Generate the SSH key**:
   ```bash
   ssh-keygen -t ed25519 -C "your-email@example.com"
   ```
   Press **Enter** to accept the default file location.

2. **Start the SSH agent**:
   ```bash
   eval "$(ssh-agent -s)"
   ```

3. **Add the SSH private key to the agent**:
   ```bash
   ssh-add ~/.ssh/id_ed25519
   ```

4. **Copy the SSH public key to your clipboard**:
   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```

5. **Add the key to GitHub**:
   - Go to [GitHub SSH Settings](https://github.com/settings/keys), click **New SSH Key**, and paste the copied public key.

6. **Test the SSH connection**:
   ```bash
   ssh -T git@github.com
   ```

---

## Step 3: Cloning a GitHub Repository Locally

You can now clone your GitHub repository using SSH or HTTPS.

```bash
git clone git@github.com:username/repository-name.git
```

Navigate to the repository directory:
```bash
cd repository-name
```

---

## Step 4: Making Changes to the `main` Branch

1. **Edit or add files in the repository**.
2. **Stage the changes**:
   ```bash
   git add .
   ```

3. **Commit the changes**:
   ```bash
   git commit -m "Your commit message"
   ```

4. **Push changes to the `main` branch on GitHub**:
   ```bash
   git push origin main
   ```

---

## Step 5: Pulling Changes from GitHub

To ensure your local `main` branch is up to date with any changes made on GitHub:

```bash
git pull origin main
```

---

## Step 6: Creating and Switching to a New Branch (`edits`)

1. **Create a new branch**:
   ```bash
   git checkout -b edits
   ```

2. **Make changes in the `edits` branch** (e.g., add files, modify files).

3. **Stage and commit your changes**:
   ```bash
   git add .
   git commit -m "Your commit message for the edits branch"
   ```

4. **Push the `edits` branch to GitHub**:
   ```bash
   git push origin edits
   ```

---

## Step 7: Merging the `edits` Branch into `main`

Once you're satisfied with your changes on the `edits` branch, you can merge them into the `main` branch.

1. **Switch to the `main` branch**:
   ```bash
   git checkout main
   ```

2. **Pull the latest changes from the remote `main` branch** (to ensure it's up to date):
   ```bash
   git pull origin main
   ```

3. **Merge the `edits` branch into `main`**:
   ```bash
   git merge edits
   ```

4. **Push the merged changes to GitHub**:
   ```bash
   git push origin main
   ```

---

## Step 8: Deleting the `edits` Branch (Optional)

Once the `edits` branch is merged, you can delete it if it's no longer needed.

1. **Delete the local `edits` branch**:
   ```bash
   git branch -d edits
   ```

2. **Delete the `edits` branch from GitHub**:
   ```bash
   git push origin --delete edits
   ```

---

## Recap of the Main Commands Used:

1. **Set Git username and email**:
   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "your-email@example.com"
   ```

2. **Generate and add SSH key**:
   ```bash
   ssh-keygen -t ed25519 -C "your-email@example.com"
   eval "$(ssh-agent -s)"
   ssh-add ~/.ssh/id_ed25519
   cat ~/.ssh/id_ed25519.pub
   ```

3. **Clone a repository**:
   ```bash
   git clone git@github.com:username/repository-name.git
   ```

4. **Stage and commit changes**:
   ```bash
   git add .
   git commit -m "Your commit message"
   ```

5. **Push changes to GitHub**:
   ```bash
   git push origin main
   ```

6. **Pull changes from GitHub**:
   ```bash
   git pull origin main
   ```

7. **Create and switch to a new branch**:
   ```bash
   git checkout -b edits
   ```

8. **Merge `edits` into `main`**:
   ```bash
   git checkout main
   git merge edits
   ```

9. **Delete the `edits` branch**:
   ```bash
   git branch -d edits
   git push origin --delete edits
   ```


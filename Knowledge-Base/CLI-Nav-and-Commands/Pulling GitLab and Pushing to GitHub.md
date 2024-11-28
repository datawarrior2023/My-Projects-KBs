### **Final Workflow Commands Summary**
Here’s the complete set of commands executed:

```bash
# Clone the GitLab repository
git clone https://git.bootcampcontent.com/Columbia-University/CU-VIRT-CYBER-PT-02-2024-U-LOLC.git

# Navigate to the cloned repository
cd CU-VIRT-CYBER-PT-02-2024-U-LOLC

# Fix "dubious ownership" error
git config --global --add safe.directory '/mnt/d/OneDrive/GH_Repositories/CU-VIRT-CYBER-PT-02-2024-U-LOLC'

# Add GitHub as the remote or update the remote
git remote set-url origin https://github.com/datawarrior2023/CU-VIRT-CYBER-PT-02-2024-U-LOLC.git

# Verify remotes
git remote -v

# Set the main branch
git branch -M main

# Push the repository to GitHub
git push -u origin main

# Optional: Push all branches and tags
git push origin --all
git push origin --tags

# Configure Git to store credentials
git config --global credential.helper store

# Pull from GitHub to verify sync
git pull origin main
```

---

### **1. Clone the GitLab Repository**
Start by cloning the GitLab repository into your local directory.

```bash
git clone https://git.bootcampcontent.com/Columbia-University/CU-VIRT-CYBER-PT-02-2024-U-LOLC.git
```

When prompted, provide your **GitLab username** and **password**. Once cloned, you’ll see the repository folder in your target directory.

---

### **2. Navigate to the Cloned Repository**
Change into the directory of the cloned repository:

```bash
cd CU-VIRT-CYBER-PT-02-2024-U-LOLC
```

---

### **3. Fix "Dubious Ownership" Error**
Mark the directory as safe for Git:

```bash
git config --global --add safe.directory '/mnt/d/OneDrive/GH_Repositories/CU-VIRT-CYBER-PT-02-2024-U-LOLC'
```

This resolves the `detected dubious ownership` error.

---

### **4. Add GitHub as a Remote**
If a remote named `origin` already exists (pointing to GitLab), update it to point to your GitHub repository:

```bash
git remote set-url origin https://github.com/datawarrior2023/CU-VIRT-CYBER-PT-02-2024-U-LOLC.git
```

Verify the remotes:

```bash
git remote -v
```

You should see:
```
origin  https://github.com/datawarrior2023/CU-VIRT-CYBER-PT-02-2024-U-LOLC.git (fetch)
origin  https://github.com/datawarrior2023/CU-VIRT-CYBER-PT-02-2024-U-LOLC.git (push)
```

---

### **5. Set the Main Branch**
Rename the default branch to `main` if it's not already:

```bash
git branch -M main
```

---

### **6. Authenticate with GitHub**
GitHub requires a **Personal Access Token (PAT)** for authentication.

#### Generate a Personal Access Token:
1. Go to [GitHub Personal Access Tokens](https://github.com/settings/tokens).
2. Click **"Generate new token (classic)"**.
3. Select `repo` as the scope and generate the token.
4. Copy the token.

---

### **7. Push to GitHub**
Use the token as your password when prompted. Push the `main` branch to GitHub:

```bash
git push -u origin main
```

When prompted:
- **Username**: Your GitHub username (e.g., `datawarrior2023@gmail.com`).
- **Password**: Paste the Personal Access Token.

---

### **8. Configure Credential Storage (Optional)**
To avoid entering credentials repeatedly, configure Git to store them:

```bash
git config --global credential.helper store
```

This stores the credentials securely for future use.

---

### **9. Push All Branches and Tags (Optional)**
To push all branches and tags to GitHub:

```bash
git push origin --all
git push origin --tags
```

---

### **10. Verify the Migration**
Check your GitHub repository to ensure the files, branches, and history have been successfully transferred.

---

### **11. Pull from GitHub to Confirm Sync**
Verify everything is up to date by pulling from the GitHub repository:

```bash
git pull origin main
```




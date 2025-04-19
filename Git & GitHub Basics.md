

Table of Contents

1. Introduction to Git and GitHub


2. Differences Between Git and GitHub


3. Installing Git and GitHub Desktop


4. Connecting Local PC to GitHub


5. Creating a New Repository


6. Basic Git Workflow


7. Branching in Git


8. Pulling and Merging Changes


9. Resolving Merge Conflicts


10. Understanding Git Version Control


11. Creating a GitHub Repository Using cURL


12. Accessing GitHub from Local PC


13. Logging Out of Git in an Initialized Folder




---

1. Introduction to Git and GitHub

Git is a distributed version control system that allows developers to track changes in their codebase, collaborate with others, and manage project history efficiently.

GitHub is a cloud-based platform that hosts Git repositories, providing tools for collaboration, code review, and project management.


---

2. Differences Between Git and GitHub


---

3. Installing Git and GitHub Desktop

Installing Git

1. Download Git: Visit the official Git website and download the installer for your operating system.


2. Install Git: Run the installer and follow the setup instructions. Default settings are recommended for beginners.


3. Verify Installation: Open your terminal or command prompt and run:

git --version

You should see the installed Git version.



Installing GitHub Desktop

1. Download GitHub Desktop: Visit the GitHub Desktop download page and download the installer for your OS.


2. Install GitHub Desktop: Run the installer and follow the setup instructions.


3. Sign In: Open GitHub Desktop and sign in with your GitHub account.




---

4. Connecting Local PC to GitHub

Using Personal Access Token (PAT)

1. Generate PAT:

Navigate to GitHub Settings.

Click on "Generate new token".

Select scopes (permissions) as needed and generate the token.



2. Configure Git:

When prompted for a password during Git operations, use the PAT instead of your GitHub password.




Using SSH Connection

1. Generate SSH Key:

ssh-keygen -t ed25519 -C "your_email@example.com"

Press Enter to accept default file location and set a passphrase if desired.


2. Add SSH Key to ssh-agent:

eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519


3. Add SSH Key to GitHub:

Copy the SSH key to your clipboard:

cat ~/.ssh/id_ed25519.pub

Navigate to GitHub SSH Settings and click "New SSH key".

Paste your key and save.



4. Test SSH Connection:

ssh -T git@github.com

You should see a success message confirming authentication.




---

5. Creating a New Repository

Using GitHub Website

1. Navigate to GitHub: Go to github.com and sign in.


2. Create Repository:

Click on the "+" icon in the top-right corner and select "New repository".

Enter repository name and description.

Choose visibility (public/private) and initialize with a README if desired.

Click "Create repository".




Using Command Line

1. Initialize Local Repository:

mkdir my-project
cd my-project
git init


2. Create Repository on GitHub:

Using GitHub CLI:

gh repo create my-project --public

Follow prompts to complete creation.



3. Link Local to Remote:

git remote add origin git@github.com:your_username/my-project.git




---

6. Basic Git Workflow

7. Initialize Git Repository:

git init


2. Check Status:

git status


3. Add Files to Staging Area:

git add filename

Or add all files:

git add .


4. Commit Changes:

git commit -m "Your commit message"


5. Push to Remote Repository:

git push -u origin main




---

7. Branching in Git

Creating a New Branch

git branch new-branch-name

Or create and switch to the new branch:

git checkout -b new-branch-name

Switching Between Branches

git checkout branch-name

Or using the newer command:

git switch branch-name


---

8. Pulling and Merging Changes

Pulling Changes from Remote

git pull origin branch-name

This command fetches and merges changes from the specified branch on the remote repository.

Merging Branches

1. Switch to Target Branch:

git checkout main


2. Merge Feature Branch:

git merge feature-branch




---

9. Resolving Merge Conflicts

10. Identify Conflicts: After a merge, Git will indicate files with conflicts.


11. Open Conflicted Files: Conflicted areas will be marked like this:

<<<<<<< HEAD
Current changes
=======
Incoming changes
>>>0




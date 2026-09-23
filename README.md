# A02: How to Use Git, WebStorm, and GitHub

This is a step by step tutorial for anyone who has never used **Git** or **GitHub** before. By the end you'll be able to set everything up, make changes to a project in WebStorm, and send those changes to GitHub. There's a glossary at the bottom if any of the terms are confusing.

---

## Part 1: Directions on Using WebStorm with Git and GitHub

### Step 1: Make a GitHub account

1. Go to https://github.com and click Sign up.
2. Enter your email, make a password, and pick a username. For this class your username should be your UCID.
3. Verify your email by clicking the link GitHub sends you.

### Step 2: Download and install Git

**Git** is the program that actually tracks your changes. WebStorm uses it behind the scenes.

1. Go to https://git-scm.com/downloads and download the version for your computer (Windows, Mac, or Linux).
2. Run the installer. On Windows the default options are fine, just keep clicking Next.
3. To check it worked, open Terminal (Mac) or Command Prompt (Windows) and type:

   ```
   git --version
   ```

   If you see something like `git version 2.x.x` you're good.

4. Tell Git who you are so your work has your name on it:

   ```
   git config --global user.name "Your Name"
   git config --global user.email "youremail@njit.edu"
   ```

   Use the same email you used for GitHub.

### Step 3: Download and install WebStorm

WebStorm is a code editor made by JetBrains that has Git built right into it.

1. Go to https://www.jetbrains.com/webstorm/download/ and download it.
2. Students can get a free license at https://www.jetbrains.com/community/education/ by signing up with your school email.
3. Install it and open it up. Sign in with your JetBrains account when it asks.

### Step 4: Create a repository on GitHub

A **repository** is basically a project folder that Git keeps track of.

1. On GitHub, click the + in the top right corner and pick New repository.
2. Name it `A02` (capital A, it matters).
3. Set it to Public and check the box to add a README file.
4. Click Create repository.

Your repo link will look like `https://github.com/yourUCID/A02`.

### Step 5: Clone the repository into WebStorm

To **clone** means to download a full copy of a **repository** from **GitHub** onto your computer.

1. On your repo page on GitHub, click the green Code button and copy the HTTPS link.
2. In WebStorm, on the Welcome screen click Clone Repository (older versions call it Get from VCS).
3. Paste the link into the URL box, pick where you want the folder saved, and click Clone.
4. If WebStorm asks you to log in to GitHub, click Log In via GitHub and approve it in your browser.
5. The project opens and you can see README.md in the file list on the left.

The copy on GitHub is now your **remote**, which just means the version of the project that lives online.

### Step 6: Make changes and commit them

1. Open README.md in WebStorm and type something in it.
2. Save the file (Ctrl+S on Windows, Cmd+S on Mac).
3. Go to Git > Commit in the top menu (or press Ctrl+K / Cmd+K).
4. Check the box next to README.md, then type a clear message, like:

   ```
   Feature: added workflow for using github
   ```

5. Click Commit.

A **commit** is like a save point. It records what changed and your message explaining why. Good messages start with a label like `Task:`, `Feature:`, or `Fix:` so people can tell what kind of change it was.

### Step 7: Push your commits to GitHub

Committing only saves the change on your computer. To get it onto **GitHub** you have to **push**.

1. Go to Git > Push (or press Ctrl+Shift+K / Cmd+Shift+K).
2. WebStorm shows you the commits that are about to go up. Click Push.
3. Refresh your repo page on GitHub and you'll see your changes.

### Step 8: Fetch and pull changes from GitHub

If someone else changes the project (or you edit it on the GitHub website), your computer won't know until you ask.

1. To **fetch**, go to Git > Fetch. This checks GitHub for new changes but doesn't touch your files yet.
2. To **pull**, go to Git > Pull and click Pull. This downloads the changes and adds them to your files.

A good habit is to **pull** before you start working so you're always on the newest version.

### Step 9: Make a branch

A **branch** lets you work on something new without messing up the main version of the project.

1. Click the branch name at the top of WebStorm (it probably says `main`).
2. Pick New Branch, give it a name like `glossary-update`, and click Create.
3. Now any **commit** you make goes on that **branch** instead of `main`.
4. When you **push**, WebStorm will create the **branch** on GitHub too.

### Step 10: Merge your branch back into main

When your work on the **branch** is done, you **merge** it back.

1. Click the branch name at the top and switch back to `main` (click main > Checkout).
2. Click the branch name again, find your branch (like `glossary-update`), and pick Merge 'glossary-update' into 'main'.
3. **Push** so GitHub gets the merged version.

### Step 11: Fixing a merge conflict

A **merge conflict** happens when two versions changed the same line and Git can't decide which one to keep.

1. If there's a conflict, WebStorm pops up a Conflicts window.
2. Click Merge... and you'll see three panels: your version on the left, the other version on the right, and the result in the middle.
3. Click the arrows to pick which changes to keep, or type the fix yourself in the middle panel.
4. Click Apply, then **commit** and **push** like normal.

---

## Part 2: Glossary

- **Branch**: A separate line of work in a repository. It lets you try new things or build features without changing the main version until you're ready.
- **Clone**: Making a full copy of a remote repository on your own computer, including all its files and history.
- **Commit**: A saved snapshot of your changes with a message describing what you did. It's like a checkpoint you can go back to.
- **Fetch**: Downloading info about new changes from the remote without adding them to your own files yet.
- **GIT**: A free version control system that tracks changes to files over time so you can see history, go back to old versions, and work with other people.
- **Github**: A website that hosts Git repositories online so you can store, share, and collaborate on projects.
- **Merge**: Combining the changes from one branch into another branch.
- **Merge Conflict**: When Git can't automatically combine two sets of changes because they edited the same part of a file, so a person has to pick what to keep.
- **Push**: Sending your local commits up to the remote repository, like GitHub.
- **Pull**: Downloading changes from the remote and merging them into your local files. It's basically a fetch plus a merge.
- **Remote**: A version of your repository that's stored somewhere else, usually online on GitHub. The default one is called `origin`.
- **Repository**: A project folder tracked by Git that holds all the files plus the full history of every change.

---

## References

1. Chacon, S., & Straub, B. *Pro Git* (2nd ed.). Apress. https://git-scm.com/book/en/v2
2. Git. *Git Documentation*. https://git-scm.com/doc
3. Git. *Downloads*. https://git-scm.com/downloads
4. GitHub. *GitHub Docs: Get started*. https://docs.github.com/en/get-started
5. GitHub. *About merge conflicts*. https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/about-merge-conflicts
6. JetBrains. *WebStorm Help: Version control*. https://www.jetbrains.com/help/webstorm/version-control-integration.html
7. JetBrains. *Download WebStorm*. https://www.jetbrains.com/webstorm/download/

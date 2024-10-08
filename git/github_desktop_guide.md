# GitHub Desktop Guide

GitHub Desktop is a user-friendly application that simplifies the use of Git. This guide will walk you through the steps to set up and use GitHub Desktop for your assignments, including those provided through GitHub Classroom.

---

## Table of Contents

1. [Installation](#installation)
2. [Setting Up GitHub Desktop](#setting-up-github-desktop)
3. [Accepting a GitHub Classroom Assignment](#accepting-a-github-classroom-assignment)
4. [Cloning Your Assignment Repository](#cloning-your-assignment-repository)
5. [Making Changes and Committing](#making-changes-and-committing)
6. [Pushing Changes](#pushing-changes)
7. [Pulling Changes](#pulling-changes)
8. [Resources](#resources)
9. [Tips](#tips)
10. [Example Workflow](#example-workflow-for-assignments)

---

## Installation

### Download GitHub Desktop

- **Windows and macOS**: [Download GitHub Desktop](https://desktop.github.com/)

### Install the Application

- Run the installer and follow the on-screen instructions.

---

## Setting Up GitHub Desktop

1. **Sign In to GitHub**

   - Open GitHub Desktop.
   - Go to **File > Options** (Windows) or **GitHub Desktop > Preferences** (macOS).
   - Sign in with your GitHub account.

2. **Configure Git**

   - Set your name and email, which will appear in your commits.

     ```plaintext
     Name: Your Name
     Email: you@example.com
     ```

---

## Accepting a GitHub Classroom Assignment

1. **Receive the Assignment Link**

   - Your instructor will provide a link to the GitHub Classroom assignment.

2. **Accept the Assignment**

   - Click on the assignment link provided by your instructor.
   - You will be redirected to GitHub Classroom.
   - Click on the **"Accept this assignment"** button.
   - Wait for GitHub Classroom to create your personal repository. Once it's ready, you'll see a confirmation message with a link to your repository.

---

## Cloning Your Assignment Repository

1. **Open Your Repository in GitHub**

   - Click on the repository link provided after accepting the assignment.
   - Ensure you're logged into your GitHub account.

2. **Clone the Repository Using GitHub Desktop**

   - On the repository page, click on the green **"Code"** button.
   - In the dropdown, click on **"Open with GitHub Desktop"**.

     - If prompted, allow your browser to open GitHub Desktop.

   - **Alternatively**, you can copy the repository URL:

     - Click **"Code"** > **"HTTPS"** > **Copy** the URL.
     - Open GitHub Desktop.
     - Go to **File > Clone Repository**.
     - In the **URL** tab, paste the repository URL.
     - Choose a **Local Path** where you want to store the repository on your computer.
     - Click **"Clone"**.

---

## Making Changes and Committing

1. **Make Changes**

   - Open your project folder in your code editor.
   - Modify files as required by the assignment, such as `pattern_generator.py` or `DOCUMENTATION.md`.

2. **View Changes in GitHub Desktop**

   - GitHub Desktop will automatically detect changes in your repository.
   - Changed files will appear under the **"Changes"** tab.
   - Click on a file to see what has changed.

3. **Stage Changes**

   - Ensure the checkboxes next to the files you want to include in the commit are selected.

4. **Commit Changes**

   - At the bottom left, write a **Summary** of your changes, e.g., "Complete Task 1: Initialize blank canvas".
   - Optionally, add a more detailed **Description**.
   - Click **"Commit to main"**.

---

## Pushing Changes

1. **Push to GitHub**

   - After committing, click **"Push origin"** in the top toolbar.
   - Your commits will be uploaded to your GitHub repository.

2. **Confirm on GitHub**

   - Go to your repository on GitHub to verify that your changes have been pushed.
   - Refresh the page to see the latest commits and file changes.

---

## Pulling Changes

If your instructor provides updates or feedback via GitHub, you may need to pull changes:

1. **Fetch Origin**

   - In GitHub Desktop, click **"Fetch origin"** to check for any new changes on GitHub.

2. **Pull Changes**

   - If there are new commits, click **"Pull origin"** to update your local repository.
   - Resolve any merge conflicts if they arise.

---

## Resources

- [GitHub Desktop Documentation](https://docs.github.com/en/desktop)
- [GitHub Classroom Student Guide](https://docs.github.com/en/education/manage-coursework-with-github-classroom/teach-with-github-classroom/student-guide-to-github-classroom)
- [GitHub Learning Lab](https://lab.github.com/)

---

## Tips

- **Commit Regularly**: Make frequent commits with clear messages to track your progress and make it easier to identify issues.

- **Sync Often**: Push your commits regularly to ensure your instructor can see your latest work.

- **Check Deadlines**: Ensure you push your final commits before the assignment deadline.

- **Backup Your Work**: Since your work is stored on GitHub, pushing your commits serves as a backup.

- **Ask for Help**: If you encounter issues, consult the resources or ask your instructor for assistance.

---

## Example Workflow for Assignments

1. **Accept the Assignment**

   - Click on the GitHub Classroom link provided by your instructor.
   - Accept the assignment and wait for your personal repository to be created.

2. **Clone the Repository**

   - Open the repository link in your browser.
   - Click **"Code"** > **"Open with GitHub Desktop"** or copy the URL and clone via GitHub Desktop.

3. **Set Up Your Local Environment**

   - Open the cloned repository folder in your code editor.

4. **Work on the Assignment**

   - Follow the assignment instructions.
   - Modify the necessary files and save your changes.

5. **Commit Your Changes**

   - In GitHub Desktop, review the changes.
   - Write a clear commit message summarizing the work done.
   - Click **"Commit to main"**.

6. **Push Your Changes**

   - Click **"Push origin"** to upload your commits to GitHub.

7. **Repeat as Necessary**

   - Continue making changes, committing, and pushing until the assignment is complete.

8. **Final Submission**

   - Ensure all your work is committed and pushed before the deadline.
   - You can verify your submission by checking your repository on GitHub.

---

## Additional Notes on GitHub Classroom

- **Private Repositories**

  - Your assignment repository is private. Only you and your instructor (and any teaching assistants) can see it.

- **Feedback and Grades**

  - Your instructor may provide feedback via GitHub issues or pull requests. Check your repository regularly for any comments.

- **Collaborative Assignments**

  - If the assignment is a group project, GitHub Classroom may assign you to a team repository. The workflow remains similar.

---

By integrating GitHub Desktop with GitHub Classroom, you streamline your assignment workflow, making it easy to manage your code and submit your work efficiently.

---

*Note: Even though GitHub Desktop simplifies the process, understanding basic Git commands can be beneficial. You can refer to the [Git Cheat Sheet](../git/git_cheat_sheet.md) for command-line examples.*
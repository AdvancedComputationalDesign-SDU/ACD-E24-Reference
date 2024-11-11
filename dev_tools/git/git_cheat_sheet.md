# git Cheat Sheet

This cheat sheet provides a quick reference to common Git commands. Even if you're using GitHub Desktop, understanding these commands can enhance your comprehension of version control.

---

## Basic Git Commands

### Setting Up Git

- **Configure your username and email**

  ```bash
  git config --global user.name "Your Name"
  git config --global user.email "you@example.com"
  ```

### Starting a Repository

- **Initialize a new Git repository in your project directory**

  ```bash
  git init
  ```

### Checking Status

- **View the status of your files**

  ```bash
  git status
  ```

### Adding Changes

- **Add a specific file to staging**

  ```bash
  git add my_code.py
  ```

- **Add all changes in the current directory**

  ```bash
  git add .
  ```

### Committing Changes

- **Commit changes with a message**

  ```bash
  git commit -m "Add initial version of my_code.py"
  ```

### Connecting to a Remote Repository

- **Add a remote repository (replace the URL with your repository URL)**

  ```bash
  git remote add origin https://github.com/yourusername/your-repo-name.git
  ```

### Pushing Changes

- **Push your commits to the remote repository**

  ```bash
  git push -u origin main
  ```

### Pulling Changes

- **Update your local repository with changes from the remote repository**

  ```bash
  git pull
  ```

### Cloning a Repository

- **Clone a repository to your local machine**

  ```bash
  git clone https://github.com/username/repo-name.git
  ```

---

## Example Workflow

1. **Initialize Git in your project folder**

   ```bash
   git init
   ```

2. **Create or modify files**

   - Edit `my_code.py`
   - Update `README.md`

3. **Check the status of your repository**

   ```bash
   git status
   ```

4. **Stage your changes**

   - Add specific files:

     ```bash
     git add my_code.py
     git add README.md
     ```

   - Or add all changes:

     ```bash
     git add .
     ```

5. **Commit your changes**

   ```bash
   git commit -m "Implement array manipulation and update documentation"
   ```

6. **Connect to your GitHub repository**

   ```bash
   git remote add origin https://github.com/yourusername/Assignment1.git
   ```

7. **Push your commits to GitHub**

   ```bash
   git push -u origin main
   ```

---

## Tips

- **Commit Often**: Frequent commits with descriptive messages help track your project's evolution.
- **Use `.gitignore`**: Create a `.gitignore` file to exclude files you don't want to track, like temporary files or sensitive information.
- **Branching** (Advanced): Use branches to work on new features without affecting the main codebase.

---

## Helpful Commands

- **View Commit History**

  ```bash
  git log
  ```

- **View Changes**

  ```bash
  git diff
  ```

- **Undo Last Commit (while keeping changes staged)**

  ```bash
  git reset --soft HEAD~1
  ```

- **Revert Changes in a File**

  ```bash
  git checkout -- filename
  ```

---

## Resources

- [Git Documentation](https://git-scm.com/doc)
- [Pro Git Book](https://git-scm.com/book/en/v2)

---

*Note: While Git commands offer powerful control, using GitHub Desktop simplifies many of these tasks with a graphical interface. Refer to the [GitHub Desktop Guide](GitHub_Desktop_Guide.md) for more information.*

---
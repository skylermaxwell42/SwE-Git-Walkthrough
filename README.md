# SwE-Git-Walkthrough
Instructional repository for walking through how to utilize revision control to optimize the software development process.


## Git Walkthrough

1. Initialize a local repository

    ```bash
    mkdir git-walkthrough/ && cd git-walkthrough
    git init
    ```

2. Add a remote repository

    Here we will tell Git to point to the link `https://github.com/skylermaxwell42/SwE-Git-Walkthrough.git` when the remote name `github` is used.

    - Command: `git remote add <remote name> <URL>`

    ```bash
    git remote add github https://github.com/skylermaxwell42/SwE-Git-Walkthrough.git
    ```

3. Pull remote repository from GitHub

    To pull from the remote repo we pointed to in the previous step we will tell git to pull from the `github` remote into our `master` branch.

    - Command: `git pull <remote name> <local branch>`

    ```bash
    git pull github master
    ```

4. Create a new feature branch

    We want to implement a new feature into our project. It's best practice to isolate the development environment while developing branches so we don't introduce bugs or errors into our working code base. Here we will create and checkout a new branch to develop our feature on.

    - Command: `git branch <branch name>`

    ```bash
    git branch feature1
    git checkout feature1
    ```

5. Implement feature1

```bash
# Creates empty file
touch src/feature1.rb
rm src/xyz.rb
```

6. Track changes

```bash
git add src/feature1.rb
git add src/xyz.rb
```

7. Commit changes to local repository

```bash
git commit -m "Implemented feature1"
```

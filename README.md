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

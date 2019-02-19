# SwE-Git-Walkthrough
Instructional repository for walking through how to utilize revision control to optimize the software development process.


## Git Walkthrough

### Initial Setup

1. Register name and email with Git

    ```bash
    git config --global user.name "First Last"
    git config --global user.email firstlast@example.com
    ```
### Set Up Project Repository

2. Initialize a local repository

    ```bash
    mkdir git-walkthrough/ && cd git-walkthrough
    git init
    ```

3. Add a remote repository

    Here we will tell Git to point to the link `https://origin.com/skylermaxwell42/SwE-Git-Walkthrough.git` when the remote name `origin` is used.

    - Command: `git remote add <remote name> <URL>`

    ```bash
    git remote add origin https://github.com/skylermaxwell42/SwE-Git-Walkthrough.git
    ```

4. Pull remote repository from origin

    To pull from the remote repo we pointed to in the previous step we will tell git to pull from the `origin` remote into our `master` branch.

    - Command: `git pull <remote name> <local branch>`

    ```bash
    git pull origin master
    ```

    Note: The previous steps can be be performed in one command, `git pull https://github.com/skylermaxwell42/SwE-Git-Walkthrough.git`, however doesn't offer as much versatility.


### Implementing a Feature with branches

5. Create a new feature branch

    We want to implement a new feature into our project. It's best practice to isolate the development environment while developing branches so we don't introduce bugs or errors into our working code base. Here we will create and checkout a new branch to develop our feature on.

    - Command: `git branch <branch name>`

    ```bash
    git branch feature1
    git checkout feature1
    ```

6. "Implement" `feature1`

    ```bash
    # Creates empty file
    touch src/feature1.rb
    rm src/xyz.rb
    ruby src/generate_data.rb
    ```
    Notice how a file has been generated in your directory.
    But wait .... we have just generated some data within the repository directory that we dont want to check into our

7. Track changes

    - Command: `git add [<file_path>, ... ]`

    ```bash
    git add src/feature1.rb
    git add src/xyz.rb
    ```

8. Commit changes to local repository

    - Command: `git commit -m "<message>"`

    ```bash
    git commit -m "Implemented feature1"
    ```

    Note: If this was a real project we would normally push to our remote, `origin`, but push access is not available for this repo. The Git push command is `git push `


9. Merge changes into master

    - Commands: `git checkout <branch name>`, `git merge <dst branch name> <src branch name>`

    ```bash
    git checkout master
    git merge master feature1
    ```

    Use the command `ls src/` to see that the changes we made in `feature1` have been merged into our `master` branch.

10. Sync some other feature branch with master

    Often when some feature is implemented and pushed into the `master` branch it may be useful to sync `master` with another working feature branch. Here we will fetch and checkout `feature2` branch and then merge the changes we to `origin` into `feature2`.

    - Command: `git fetch <remote name> <remote branch name>`

    ```bash
    git fetch origin feature2
    git checkout feature2
    git merge feature2 origin
    ```

    Use the `ls src/` command to see that the changes made in `feature1` branch are reflected now in `feature2` branch.

#### GitHub Repository Model 
- This is a Distributed Version-control system.
- The Main focus of GitHub is to track the source code.
- GitHub helps to coordinates among programmers to
	- To Track Changes on codes.
	- Support Non-Linear Workflows.

#### Git
- Git is a distributed version-control system.
	- Tracks changes to content.
	- provides a central point for collaboration.
- Git allows for centralized administration
	- Teams have controlled access scope.
	- The Main Branch consists of deployable code, multiple branches can be created to code test features, once the features finalized test features code merged main branch.


Creating a repository
- **Log in to your GitHub Account:** Go to [https://github.com](https://github.com/) and sign in.
- **Click the "New" button**: In the top right corner, click the green "New" button.
			![[Pasted image 20240613223137.png |250]]\ 
- GitHub home page with New button highlighted.
- **Fill in the repository details**:
	- Repository name: Choose a descriptive name for your project.
	- **Description (optional):** Add a brief overview of your repository.
	- **Visibility:** Select whether the repository will be public or private.
	- **Initialize this repository with a README:** Check this box to create a README file automatically.
- **Click** "Create repository": This creates your empty repository on GitHub.

**Editing Files**
- **Navigate to the file**: In your repository, find the file you want to edit.
- **Click the pencil icon**: Next to the file name, click the pencil icon to open the file editor.
			![[Pasted image 20240613223740.png |  250]] 
- **Make your changes**: Modify the file's content as needed.
- **Commit your changes:**
	- Click the "**Commit changes**" button.
    - Enter a clear and concise commit message describing your changes.
    - Click "Commit changes" again to save your work.
			![[Pasted image 20240613224054.png]]

- **Uploading Files:**

- **Drag and drop or browse:**
    - Drag and drop files directly onto the file list in your repository.
    - Or, click the "Add file" button and select files from your computer.
			![[Pasted image 20240613224324.png]]
    - GitHub repository with Add file button highlighted
        
- **Enter a commit message:** Describe the changes you're making in the commit message box.
- **Click "Commit changes":** This uploads the files to your repository and saves the changes.
    

**Additional Notes:**
- **Creating a README file:** A README file provides important information about your project. It's often the first thing people see when visiting your repository.
- **Using branches:** Branches allow you to work on different features or versions of your code without affecting the main version.
- **Merging branches:** Once you're done working on a branch, you can merge it back into the main branch to incorporate your changes.
- **Pull requests:** When collaborating with others, pull requests allow you to propose changes to the code and have them reviewed before merging.

#### GIT Commands 

**Basic Commands:**
- **git init:** Initializes a new Git repository in the current directory.
- **git status:** Shows the current status of the working tree, including modified files and untracked files.
- **git add:** Adds files or changes to the staging area for the next commit.
- **git commit:** Commits the staged changes to the repository, creating a new snapshot of the project.
- **git branch:** Manages branches, including listing, creating, and deleting branches.
- **git checkout:** Switches between branches or restores files from a specific commit.
- **git merge:** Merges changes from one branch into another.
- **git push:** Pushes commits from your local repository to a remote repository.
- **git pull:** Fetches and merges changes from a remote repository to your local repository.
- **git log:** Displays the commit history of the repository.

**Additional Commands:**
- **git clone:** Clones an existing remote repository to your local machine.
- **git diff:** Shows differences between files, commits, or branches.
- **git reset:** Undoes changes to files or commits.
- **git rm:** Removes files from the working tree and staging area.
- **git stash:** Temporarily shelves changes to be reapplied later.
- **git config:** Configures Git settings, such as your username and email.
- **git remote:** Manages remote repositories, such as adding or removing remotes.


**Remember:**

- Use a Git client like Git Bash on Windows for a better command-line experience.
- Explore Git's comprehensive documentation for more commands and advanced usage: [https://git-scm.com/docs](https://git-scm.com/docs)
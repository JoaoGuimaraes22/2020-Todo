## Git Documentation

**Setup:**

- Download Git:
  - https://git-scm.com/downloads;
- Open Git Bash, do the following with the command line;
- Check Git Version with:
  - `git --version`;
- Set config values with:
  - `git config --global user.name "<name>"`;
  - `git config --global user.email "<email>"`;
- Optionally, to see your config values, run:
  - `git config --list`;
- If you need help, run:
  - `git help <verb>`;
  - `git <verb> --help`;

**Getting Started:**

- Intilialize a repository in a folder;
  - Open your terminal in the folder of choice;
  - Run:
    - `git init`;
- To see the new **.git folder**, you must enable, "See hidden folders";
- See what's going on with:
  - `git status`;
- Add a file named **.gitignore** to your project/folder;
  - In the **.gitignore** file, you can type the folders/files you don't wish to add to your repository:
    - See https://git-scm.com/docs/gitignore to check how to do this;

**Work with git:**

- Run `git status` if you are ever in doubt on how things are doing;
- Add your files to the staging area with:
  - `git add <file_name>`;
  - To add all your files, run:
    - `git add .` or;
    - `git add -A`;
- To remove changes from the staging area, run:
  - `git reset <file_name>` or;
  - `git rm --cached <file_name>`;
  - Remove everything from the staging are with:
    - `git reset`;
- To commit your files, first stage them, and then run:
  - `git commit -m "<descriptive changes about your commit>"`;
- See all your commits with:
  - `git log`;
- Run `git diff` to see changes between commits, commit and working tree, etc;

**Work effeciently with git:**

- Clone a remote repo (example: Github) using:
  - `git clone <url> <path_where_you_want_to_clone>`
- To see info about the remote repo, run:
  - To see what remote repos are associated with your cloned repo, and you can do with it, run:
    - `git remote -v`;
  - To see all branches locally and remotely, run:
    - `git branch -a`;
- To add a remote repo to your project, run:
  - `git remote add origin <remote_repo_url>`;
- Pushing changes:
  - First commit your files:
    - `git add .` or `git add -A`, then run;
    - `git commit -m "<descriptive_changes_about_your_commit>"`;
  - Then push:
    - `git push -u origin master`;
    - The `-u` sets your remote repo as the the **upstream** branch repo, which makes it easier to track changes;
- Optionally, add multiple remote origin repos with:
  - `git remote set-url --add --push origin <remote_repo_url>`;

**Branching and workflow:**

- When you add a branch, you basically create a clone of your original directory;
- In the branch, you can do all you can with git, and change all your files, without affecting other working trees;
- To add a branch from your current working directory, run:
  - `git branch <branch_name>`, or to be more efficient, run;
  - `git checkout -b <branch_name>`;
- To switch to your desired branch, run:
  - `git checkout <branch_name>`;
- To see all your branches, run:
  - `git branch -a`;
- You can create branches of branches;
- For example, a common git branching workflow is:
  - Main branch: `master`;
  - Development branch: `master -> dev`;
  - Feature branches: `dev -> feature/<feature_name>`;
- You can add remote branches in your remote repo as you would withn your local machine:
  - `git push -u origin dev`, creates a new remote repo branch in origin, called dev;

**Merging and pulling:**

- To merge two branches, go to the file where you want the merging to happen, and run:
  - `git merge <branch_to_be_merged>`;
- This only alters the branch you ran your command in, not the branch that was merged into it;
- There may be conflicts on a merge:
  - To fix this, you choose which changes you want to apply;
- You can fetch from a repo with:
  - `git pull origin <branch_name>`

**Helpfull optionall stuff:**

- Check this stuff out:
  - Visual Studio Code Extension - GitLens;
  - GitKraken, a free Git GUI client, voted best developer tool 2019;

**Links:**

- https://www.youtube.com/watch?v=3RjQznt-8kE&list=PL4cUxeGkcC9goXbgTDQ0n_4TBzOO0ocPR;
- https://git-scm.com/docs/
- https://www.youtube.com/watch?v=SWYqp7iY_Tc

Git is a popular version control system. It was created by Linus Torvalds in 2005, and has been maintained by Junio Hamano since then.

It is used for:
> Tracking code changes
> Tracking who made changes
> Coding collaboration

Git is a tool to work with GitHub

GitHub is the largest host of source code

git --version

Configure Git:

git config --global user.name "w3schools-test"
git config --global user.email "test@w3schools.com"

----------------------------------------------------

git clone "https://github.com/w3schools-test/w3schools-test.github.io.git" = for cloning repo

git remote add origin https://github.com/w3schools-test/hello-world.git = Push Local Repository to GitHub

git push --set-upstream origin master = pushing our master branch to the origin url, and setting it as default remote branch

git init . = initiates git directory

git status
git add (-a/--all = all )
git commit -m "any message"
git status --short = to see the changes in a more compact way

git log = Git Commit Log

git "command" -help
git help --all

git branch "hello-world-images" = New Git Branch
git checkout "hello-world-images" = switching/changing branch

git fetch origin = gets all the change history of a tracked branch/repo

git merge origin/master combines the current branch, with a specified branch

git pull origin = update your local repository

git branch -a = see all local and remote branches

git branch -r = see remote branches only

Configuring Remotes:

git remote -v

git remote rename origin upstream

git remote add origin https://github.com/kaijim/w3schools-test.github.io.git

Git Ignore:

When sharing your code with others, there are often files or parts of your project, you do not want to share.

Examples

log files
temporary files
hidden files
personal files
etc.

Git can specify which files or parts of your project should be ignored by Git using a .gitignore file.

Git will not track files and folders specified in .gitignore. However, the .gitignore file itself IS tracked by Git.

touch .gitignore

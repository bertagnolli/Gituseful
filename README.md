# Git {brackets show git commands, take them out when typing into Git}:

set username and email to ALL of your actions:
$ git config --global user.name "Your Name"
$ git config --global user.email "your_email@example.com"

Creating and editing readme md file:
$ cat > README.md to edit text. $cat >> README.md to append text
type in stuff, then CTRL+D to save and close
alternatively $ touch README.md creates an empty file
$cat README.md to read the file
$ git add README.md
$ git commit README.md -m "This is my commit message"

- Create new repo in Github website. To avoid errors, do not initialize the new repository with README, license, or gitignore files.
- Create repo: Navigate to folder using bash with {cd <path>}
- Set current path as repo using {git init}
- Add the files in your new local repository. This stages them for the first commit. {git add .}
- Commit the files that you've staged in your local repository. {git commit -m "First commit"}
- On the Webpage of Git repository, copy the .git path under code e.g. https://github.com/bertagnolli/repo.git
- In the Command prompt, add the URL for the remote repository where your local repository will be pushed. {git remote add origin <remote repository URL>}
- Verifies the new remote URL is correct {git remote -v}
- Push the changes in your local repository to GitHub. {git push origin master}

If there's already stuff in repo it might complain saying "Updates were rejected because the remote contains work that you do not have locally". You can force a push with {git push -f origin master} WARNING: THIS WILL FORCE AN OVERWRITE TO ALL EXISTING FILES IN REPO

Workaround Vivado blocking Git push:
error 403, xilinx-xhub-users-g1
I have found one workaround to this problem.  I had the git credential.helper set to store. I was able to disable that by going into my cloned github repository and typing this command.
    {git config credential.helper ""}
I had to run it in each repo but maybe it is possible to use a --system or --global option to apply the change for all cloned repos.

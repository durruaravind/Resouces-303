# Advanced git commands

## How to configure the tooling commands

### The below command will set the name of your commit transactions.

$ git config –global user.name “[name]”

### The below command will set the email to your commit transactions.

$ git config –global user.email “[email address]”

## How to create Repositories

### The below command will create a new repository with a specified name.

$ git init [project-name]

### The below command will allow you to download a project and its complete version.

$ git clone [url]

## How to refactor the file name

### The below command will delete the file from the working directory and stages the deletion.

$ git rm [file]

### The below command will allow you to delta the file from the version control but saves it locally.

$ git rm –cached [file]

### The below command will change the file name and prepare it for commit.

$ git mv [file-original] [file-renamed]

## How to suppress the tracking

### The below command will list all the ignored files within the project.

$ git ls-files –others –ignored –exclude-standard

## How to shelve and restore incomplete changes

### The below command will temporarily store all the modified tracked files.

$ git stash

### The below command will restore the most recently stashed file.

$ git stash pop

### The below command will list all the stashed changesets.

$ git stash list

### The below command will discard the most recently stashed changeset.

$ git stash drop

## Commands to erase mistakes

### The below command will undo all the commits but preserve the changes locally.

$ git reset [commit]

### The below command will discard all the history and changes back to the specific commit.

$ git reset –hard [commit]

## Commands for group changes

### The below command will display all the local branches in the current repository.

$ git branch

### The below command will allow you to create a new branch.

$ git branch [branch-name]

### The below command will delete the specified branch.

$ git branch -d [branch-name]

## Miscellaneous commands

### The below command will allow you to connect your local repository to the remote server.

$ git remote add [variable name] [Remote Server Link]

### To Split a subfolder out in a new repository.

$ git filter-branch --prune-empty --subdirectory-filter master

### To remove untracked files

$ git clean -f

### To remove untracked files/directories

$ git clean -fd

### list all files/directories that would be removed

$ git clean -nfd

## Whenver connected to proxy server, git push origin main will show error:
"fatal: unable to access 'https://github.com/durruaravind/coding-solutions.git/': Could not resolve host: github.com

SOLUTION:-
git cofig --global http.proxy mySystemIP:@ProxyIP:ProxyPort
mySystemIP= 10.32.4.180
ProxyIP= 10.32.0.1
ProxyPort= 8080
Paste: $ git cofig --global http.proxy 10.32.4.180:@10.32.0.1:8080

To check systemIP address:
Open CMD >> type ipconfig/all >> check value of IPv4 Address

To reset this bypass when you are on normal wifi:
git config --global --unset http.proxy 
git config --global --unset https.proxy

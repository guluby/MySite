# Git Notes
> Source ProGit book
## __Installation__

Install  
>`sudo apt install git-all`  

Setup(show settings)
>`git config --list --show-origin`

Identity
>`git config --global user.name "User name"`   
>`git config --global user.email name@gmail.com`

Get help
>`git help <command_name>` or `git <command> -h`

## __Git Basics__

First,**_getting a git repository_**,either create local or clone from existing repository

New directory
>cd ~/gitdir
>git init

Existing directory
>cd path/to/directory
>git add file
>git commit -m "init project"

Cloning an existing repository
>git clone `https://github.com/usrname/project` localdirname

Then,**_Checking the status of the files_**
>git status

**_Tracking New Files_**, `git add` tell git to track new files, stage files
>git add NewFile

**Ignoring Files**, `.gitignore` tell git which files patterns to ignore
>cat .gitignore  
>*.\[oa]   
>*~
<details>
    <summary><i>More examples, click to expand</i></summary>
    
[comment]: <> (use html tags to create collapse section https://gist.github.com/pierrejoubert73/902cc94d79424356a8d20be2b382e1ab)

Above example, tell git to ignore any files ending in ".o" or ".a" and also any file end with a tilde"~", another example as following

>\# ignore all .a files  
*.a  
\# but do track lib.a, even though you're ignoring .a files above  
!lib.a  
\# only ignore the TODO file in the current directory, not subdir/TODO  
/TODO  
\# ignore all files in any directory named build  
build/  
\# ignore doc/notes.txt, but not doc/server/arch.txt  
doc/*.txt  
\# ignore all .pdf files in the doc/ directory and any of its subdirectories  
doc/**/*.pdf
</details>


**Commit changes**
>git commit -m "Message for commit"  
>git commit -a -m "-a skip the staging part"

**Remove/Move files**
>git rm filename  
git mv file_from file_to

**Commit History**
>git log -p -5 `shows differences between patches, only show latest 5 changes`  
git log --pretty

**Undo**
>git commit -m "Initial commit"
git add forgotten_file
git commit --amend

**Revert change of file to previous**
*This will lose any change made to the local file*
>git checkout -- file.name

**Fetch/Pull/Push**  
Get data from remote project
>git fetch <remote>

Auto fetch and merge remote into current branch
>git pull

Sharing local changes
>git push <remote> <branch>  
>git push origin master

**Aliasing**  
Create shortcut for commonly used command
>git config --global alias.co checkout  
git config --global alias.ci commit  
git config --global alias.st status



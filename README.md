# Git-VCS
notes on version Controlling with git


## Git Vocabulary
- **commit object** - A small text file.
- **Annotated tag** - A permanent reference to a specific commit.
- **Tree** - Directories and file names in a project.
- **Blob** - The content of a file in the project.
- **Git ID's** - commit_id is known as SHA or SHA1 


## Git Graph Model
- git models the relationship of commits with a DAG.
- the directed nature is implied by the vertical order of the commits, with most recent commit on top.

<div align="center">
<img width="600" src="images/git graph DAG example.png" alt="Git DAG exmple">
</div>


branch occurs when a commit has more than one child.

merge occurs when a commit has more than one parent.


???????????????????????????????


<br/>


---
# working with git 

## initialize git vcs in local repository:
```
>> git init 
```
>_initializes git vcs in current directory_

***example:***
```
>> git init myproject
```
>_creates a new folder named myproject and initializes git vcs in it._

<br/>

## Clone a remote repository( from github ) :
***syntax:***
```
git clone source destination
```

***example:***
```
>> git clone https://github.com/LearnWebCode/welcome-to-git.git “welcome page”
```
>_clones the welcome-to-git project in directory named welcome page._

***example:***
```
>> git clone https://github.com/awesome projectdir
```
>_clones the project named awesome in directory named projectdir._

***example:***
```
>> git clone https://github.com/awesome 
```
>_clones the project named awesome in directory named awesome._


<br/>

---
## Check status of files and folders in VCS
```
>> git status
```
_The git status command will display a lot of information depending on the state of your files, the working directory, and the repository._
- tell us about new files that have been created in the Working Directory that Git hasn't started tracking, yet
- files that Git is tracking that have been modified and etc etc.

<br/>

---
## To view logs / commit history 
```
>> git log
```
	
***flags:***

```
	 	--oneline 	"shows all commits 1/line with SHA and commit message"
```

-	lists one commit per line.
-	shows the first 7 characters of the commit's SHA.
-	shows the commit's message.

```
	 	--stat		"shows stats"
```

-	displays the file(s) that have been modified.
-	displays the number of lines that have been added/removed.
-	displays a summary line with the total number of modified files and lines that have been added/removed.

```
	 	--patch    or     -p	“show what lines were added and what were removed”
```

-	displays the files that have been modified
-	displays the location of the lines that have been added/removed
-	displays the actual changes that have been made

```
>> git  log --author="sajid" 
```

_will show all logs for commits made by sajid._

```
>> git log --graph --decorate –all
```

_the default git log displays the SHA, the author, the date, and the message._

### one command to rule em all 
```
 >> git log --oneline --graph --decorate -all
```
_shows the graphical representation of all the commits made till now._


<br/>


---






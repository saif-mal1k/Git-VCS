# Git-VCS
notes on version Controlling with git


## Git Vocabulary
***Git Objects:***
- **commit object** - A small text file.
- **Annotated tag** - A permanent reference to a specific commit.
- **Tree** - Directories and file names in a project.
- **Blob** - The content of a file in the project.

_typically a user interacts with only commit and tag and let the ``Git`` deal with tree and blob._

***important notes:***
- remote -
- **Git ID's** - commit_id is a "40 character hexadecimal string" also known as hash, checksum, SHA.

<details>
<summary> 💡 <b>tip: <em>Does git use SHA-1 or sha256?</em></b></summary>
<p>
	
_At its core, the Git version control system is a content addressable filesystem. It uses the SHA-1 hash function to name content. The length of a SHA1 hash is 160 bits or 20 bytes. In this application it is represented by 40 characters in hexadecimal form. SHA-1 was cracked by google reaserchers and is considered unsafe for storing passwords._
<br/>***you can use ``>> git hash-object filename`` command to generate SHA1 hash code for any file.***
</p>
</details>

<br/>

## Git Graph Model
- git models the relationship of commits with a DAG (Directed Acyclic Graph).
- the directed nature is implied by the vertical order of the commits, with most recent commit on top.
- their is no circular loop in graph, all the commits ("child nodes") are directed from bottom to top.

<div align="center">
<img width="600" src="images/git graph DAG example.png" alt="Git DAG exmple">
<p>
	
***note:*** _out of 40 characters only first 7 characters can be used as commit ID to refer to a commit._
</p>
</div>

- **branch** occurs when a commit has more than one child.
- **merge** occurs when a commit has more than one parent.
- **``HEAD pointer``** points to the most recent commit on a branch.


<br/>


---
# working with git 

## initialize git vcs in local repository:
```
>> git init 
```
_initializes git vcs in current directory_

```
>> git init myproject
```
_creates a new folder named myproject and initializes git vcs in it._

<br/>

## Clone a remote repository( from github ) :
***syntax:*** ``>> git clone source destination``

```
>> git clone https://github.com/LearnWebCode/welcome-to-git.git “welcome page”
```
_clones the welcome-to-git project in directory named welcome page._

```
>> git clone https://github.com/awesome projectdir
```
_clones the project named awesome in directory named projectdir._

```
>> git clone https://github.com/awesome 
```
_clones the project named awesome in directory named awesome._


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
# push and pull with remote repository



<br/>

---

## tagging commits / versions
**tag is a reference/label attached to a specific commit.
<br/>the tags are used to mark a time line in history, as v1.0,beta,v1.1 or some similiar names.**
- they are of two types
- Light Weight
	- simple reference to a commit.
- Annotated Tag
	- A full git object that references a commit.
	- Includes tag author name, tag date, tag message, the commit ID.

```
>> git tag 
```
_shows the list of all the tags in the repository, if present._

```
>> git tag tagname
```
_the commit that HEAD points to (i.e the most recent commit in current branch) will be tagged with the provided tag name._

```
>> git tag -a tagname -m "your message here" 
```
_-a denoted the tag is annoted basically annotted tags have message and big description as compared to light weight tag's (tags with out -a)_


### adding tag to a past commit
***syntax:*** ``>> git tag -a tagname <commit_SHA>``

```
>> git tag -a version1 a242f45
```

### pushing tags
**note: *the ``>> git push`` command alone can not automatically transfer tags to the remote repository***
- to transfer a single tag, use  ***``>> git push <remote> <tagname>``***.
- to transfer all the tags, use ***``>> git push <remote> --tags``***.
	

### deleting a tag
```
>> git tag -d tagname 
>> git tag --delete tagname 
```
_deletes the tag from your local repo , to delete the tag from global(github,or other hosting) use command <b> ``>> git push tag -d tagname`` </b> (-d is short for --delete)._


<br/>
	
---
# branching and merging
master is the default name of the main branch in the repository.
<div align="center">
<img src="images/git status.jpeg" alt="example" width="600">
</div>

branch occurs when a commit has more than one child.



merge occurs when a commit has more than one parent.


???????????????????????????????











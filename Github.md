Changes from past week:
#### STATUS

status #Tells you all you need to know for where you are and what changes have been made

#### LOG

```
git log --all --pretty=format:'%h %ad | %s %d [%an]' --graph --date=short

--pretty="..." defines the format of the output.
%h is the abbreviated hash of the commit
%d are any decorations on that commit (e.g. branch heads or tags)
%ad is the author date
%s is the comment
%an is the author name
--graph informs git to display the commit tree in an ASCII graph layout
--date=short keeps the date format nice and short
```

http://gitimmersion.com/lab_10.html

#### ALIAS'

```
co = checkout
ci = commit
st = status
br = branch
hist = log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short
```

###EDITING A FILE

```
echo "text" > file.txt #Overwrites the entire file
echo "text" >> file.txt #Appends to the file
touch newFile.txt #Creates a new file
```

####CHECKOUT AND COMMIT

```
add fileIchanged.txt #Moves the change to the staging area
commit -m "Description of change made" #Will commit the change to the git

checkout #Undoes all changes made resettubg tge directory to the last push
reset HEAD file.txt #Moves a change out of the staging area and into the working directory
reset --hard #Combines checkout and reset
```

#### PUSH & PULL

```
push #updates the github repo with your clone of the repo
pull #updates your clone of the repo with the current repo
```

####BRANCHING

```
checkout -b newBranch #Creates a new branch called newBranch
checkout master #Will switch to the new branch, in this case the master branch
```
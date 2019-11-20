# Move Commit to Another Branch

## New Branch
The process for moving work off one branch and onto a newly created branch is the simplest of the two operations.

```git
1. git checkout source-branch
2. git branch source-branch new-branch
3. git reset –hard HEAD~1
```

### Step 1
Make sure that you're on *source branch* – the branch that has the commits we want to move to a new branch. 

### Step 2 
Create a new branch that uses the source branch as its starting point. 
As a result, the new branch will have all the commits currently found in the source branch, including the changes we want moved. 
After we execute Step 2, keep in mind that we are still on the source branch and did not switch to the new branch. 

### Step 3
Delete the commit from the source branch. 
Using the `reset --hard` command allows us to revert the workspace back to the way it was at the specified commit. 
In the case of the example, we supply the shorthand `HEAD~1` which means “go back one commit from where HEAD is pointing”. 
Substituting a different number like “3” `HEAD~3` would jump things back 3 commits. 
Alternatively, you could supply an explicit commit **SHA1** value and the workspace would revert back to that commit. 
Now we’ve reached our goal state in which the new branch has the target commit and 
the source branch does not – effectively 'moving' it from one to the other.

## Existing Branch
```
1. git checkout destination-branch
2. git merge source-branch
3. git checkout source-branch
4. git reset –hard HEAD~1
```
### Step 1
Make sure you're on the branch where we want the commit to end up. 

### Step 2
Then merge in the source branch. At this point, the destination branch should have the work transferred. 

### Step 3
Move back to the source branch. 

### Step 4
Delete the commit from the source branch.

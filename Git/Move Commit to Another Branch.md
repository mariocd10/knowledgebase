# Move Commit to Another Branch

## New Branch
The process for moving work off one branch and onto a newly created branch is the simplest of the two operations.

1. `git checkout`
2. `git branch`
3. `git reset –hard HEAD~1`

### Step 1
we make sure that we are on our “source branch” – the branch that has the commits we want to move to a new branch. 

### Step 2 
Creates a new branch that uses the source branch as its starting point. 
As a result, the new branch will have all the commits currently found in the source branch, including the changes we want moved. 
After we execute step (2), keep in mind that we are still on the source branch and did not switch to the new branch. 

### Step 3
In step (3) we delete the commit from the source branch. 
Using the `reset --hard` command allows us to revert the workspace back to the way it was at the specified commit. 
In the case of the example, we supply the shorthand `HEAD~1` which means “go back one commit from where HEAD is pointing”. 
Substituting a different number like “3” (HEAD~3) would jump things back 3 commits. 
Alternatively, you could supply an explicit commit SHA1 value and the workspace would revert back to that commit. 
Now we’ve reached our goal state in which the new branch has the target commit and 
the source branch does not – effectively “moving” it from one to the other.

## Existing Branch
1. `git checkout`
2. `git merge`
3. `git checkout`
4. `git reset –hard HEAD~1`

### Step 1
In step (1) we make sure we are on the branch where we want the commit to end up. 

### Step 2
We then merge in the source branch in step (2). At this point, our target branch should have the work we want transferred. 

### Step 3
We move back to the source branch in step (3) and, as previously, 

### Step 4
We delete the commit from the source branch in step (4).

# About branchplayground
The branchplayground repository is an environment for you to get used to working with branches and a basic branch workflow. A Git branch is essentially an independent line of development that helps us to isolate work and to have control over changes made to the source code. 
## When and why are branches useful? 
Branches are particularly useful in **parallel development** and when **working in teams**: They allow us to safely divide the work among team members. Changes in the primary/default branch (main/master) or other branches do not affect your branch (unless you actively pull the latest changes from them). Therefore, branching prevents unwanted interference between changes made by different people.
By working on different branches we can develop features, fix bugs, or safely experiment in a contained area of the repository. Changes or developed features are only merged back into the main body of code (after a pull request) when added changes are tested and approved. 

# Workflow
The workflow we are using here is a so-called **feature branch workflow**. It assumes that all team members have equal knowledge and position. This workflow employs two parallel *long-running* branches:
* **```main```** 
   * Contains only entirely stable code  
* **```develop```** 
    * Developers work from this branch (features, bug fixes..) or use it to test stability
    * This branch is not necessarily always stable, but whenever it gets to a stable state, it can be merged into master. 
    * Based on this branch short-lived feature branches are created that may later be merged back into it
    
And one or many *short-lived* feature branches,  
* e.g. **```feature/feature_name```** 
    * New development (new features, non-emergency bug fixes) are built within feature branches
    * Finished features and fixes are merged back into the ```develop``` branch when they’re ready for release

which are branched off of the ```develop``` branch.

# Getting started
## What I have already done
I have already created a ```develop``` branch that you can use (A fork will contain all the branches in the main repo at the time you made the fork).
```
git branch develop
git push origin develop
```
and also added an example feature branch called ```feature/feature_no1``` - that I have used to add a "feature" to the source.md - which I merged back into the ```develop``` branch and then I merged the ```develop``` into the ```main``` branch. 
## It's your turn
**Step 0: Git**
Make sure you have [**git**](https://git-scm.com/downloads) installed on your system.
**Step 1: Forking and branch creation**
Fork the *branchplayground* repository. A fork is a copy of a repository that allows us to freely experiment with changes without affecting the original project. Then create and push the develop branch
```
git branch develop
git push origin develop
```
**Step 2: Cloning**
Create a local clone of your fork
```
git clone https://github.com/YOUR-USERNAME/branchplayground
cd branchplayground
```
**Step 3: Creation of a new feature branch**
As you are now on the ```main``` branch, switch to the ```develop``` branch.  And create a feature branch and switch from 
```
git checkout develop
git branch feature/feature_name
```
Shortcut:  ```git checkout -b feature/feature_name  ```
**Step 4: Add your feature**
Add your feature to the source.md file for example add a new line with your feature name to the file and save it. Use ``` git add``` to select the file, and to move it to the staging area (marking it for inclusion in the next commit), commit your changes and push your branch and the changes to the remote repository.
```
git add Source/source.md
git commit -am "My feature is ready"
git push origin feature/feature_name
```
Go on GitHub Web and check if you can see your changes on the feature/*feature_name* branch. 
**Step 5: Merging**
As your feature is done merge the feature branch with the develop branch and push it to the remote repository.
```
git checkout develop
git merge feature/feature_name
git push origin develop
```
Go on GitHub Web and check if you can see your changes on the develop branch. Then merge the develop branch with the main branch and push it to the remote repository.
```
git checkout main
git merge develop
git push origin main
```
Go on GitHub Web and check if you can see your changes on the develop branch

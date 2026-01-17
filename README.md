# ashif-test-repo


## Cherry Pick

Cherry-picking in Git allows you to apply a specific commit from one branch to another, without merging the entire branch. This is useful when you want to bring in a specific feature or fix from one branch to another without incorporating all the changes from the source branch.

## Usage

### Bug hotfixes

When a bug is discovered it is important to deliver a fix to end users as quickly as possible. For an example scenario,say a developer has started work on a new feature. But it has been discovered that after a production release there is bug that was identified. 

Now, it is important that we fix the production bug first else it affect end users. To do this, developer creates a specific commit for that fix in the same branch he is working on and applies the commit(bug-fix) to the main branch and deploy. This is called cherry-picking.

In other words, take a commit hash and apply to main branch so only that specific commit gets added to main branch not the entire feature branch.


Lets say on deploying this main branch the production, it has identified a bug.
And the fix for this is that one commit in feature branch which accidently did not merged.

Now if we cherry-pick that one specific commit and apply to main bug fix will be done

```
git checkout feature_branch

git log --one-line
c59d7f2 (HEAD -> feature1) 3rd commit
53f21c8 path commit
ed3cab2 2nd commit # <--this comit will fix the bug>
abbe2b6 1st commit
c26af69 first commit

git checkout main
git cherry-pick ed3cab2
```


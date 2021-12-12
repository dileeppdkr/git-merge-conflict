# Problem Statement
Hooli Co. has put Harry and Kane to implement a new set of features in their feature software. Both started working separately, making their own copies of the same source code. Now, it has become difficult for them to track the changes they’ve made in the original code,and they are finding it difficult to merge their code together

# Action Items
* Create two separate branches from master 
* Make changes in the same function of the source code in both the branches 
* Merge branch1 into the master
* Try and merge branch2 into the master (merge conflict should arise)
* Install a merge tool of your choice and resolve the merge conflict using git mergetool command


# Solution
* Created main branch and pushed local code to main branch
* Created a file (git_merge.rb) and push to main branch
* Created branch1 and modified the git_merge.rb and pushed changes to branch1
* Created branch2 and modified the git_merge.rb and pushed changes to branch2
* Merged branch1 with main branch using below steps
 ```
    git checkout -b branch1 main
    # Edit some files
    git add git_merge.rb
    git commit -m "verfying merging conflicts from dev1"
    git push origin branch1
    # Merge in the branch1 branch
    git checkout main
    git merge branch1
 ```
* Merged branch2 with main branch using below steps
```
    git checkout -b branch2 main
    # Edit some files
    git add git_merge.rb
    git commit -m "verfying merging conflicts from dev2"
    git push origin branch2
    # Merge in the branch2 branch
    git checkout main
    git merge branch2

    Auto-merging git_merge.rb
    CONFLICT (content): Merge conflict in git_merge.rb
    Automatic merge failed; fix conflicts and then commit the result.
 ```
 * Conflicts arise 
 * resolve conflicts using merge tool example: p4merge, diffmerge, kdiff3
 ```
    git mergetool
    # Resolve conflits 
    git commit -am 'merged from several branches'
    git push
 ```

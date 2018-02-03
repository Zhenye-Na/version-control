If a branch is deleted and leaves some commits unreachable from existing branches, those commits will continue to be accessible by commit id, until Git’s garbage collection runs. This will happen automatically from time to time, unless you actively turn it off. You can also run this process manually with `git gc`.


# A note about git merge
git merge will also include the currently checked-out branch in the merged version. So if you have branch1 checked out, and you run git merge branch2 branch3, the merged version will combine branch1 as well as branch2 and branch3. That’s because the branch1 label will update after you make the merge commit, so it’s unlikely that you didn’t want the changes from branch1 included in the merge. For this reason, you should always checkout one of the two branches you’re planning on merging before doing the merge. Which one you should check out depends on which branch label you want to point to the new commit.

Since the checked-out branch is always included in the merge, you may have guessed that when you are merging two branches, you don't need to specify both of them as arguments to git merge on the command line. If you want to merge branch2 into branch1, you can simply git checkout branch1 and then type git merge branch2. The only reason to type git merge branch1 branch2 is if it helps you keep better mental track of which branches you are merging.

Also, since the two branches are merged, the order in which they are typed into the command line does not matter. The key is to remember that git merge always merges all the specified branches into the currently checked out branch, creating a new commit for that branch.

## Merge conflict
If you get a message like this

```
Auto-merging game.js
CONFLICT (content): Merge conflict in game.js
Automatic merge failed; fix conflicts and then commit the result.
```

then your files were not in the same state as Caroline's when you started the merge. To fix this, complete the following steps:

- Restore your files to their state before you started the merge by running git merge --abort
- Double check the state of your files. If you run git log while the master branch is checked out, you should see Caroline's "Add color" commit as the second-most-recent, and the most recent should be your commit fixing the bullet bug. If you use git diff to compare your commit to Caroline's, your commit should introduce the line this.delayBeforeBullet = 10; on line 424. The line should be indented to the same level as the line below it using only spaces (no tabs), and the line should have no spaces after it.
- Once your file is in the correct state, create a new commit with your changes.
- Try the merge again.

Merge conflict (Newline characters between Windows and Unix systems)
Context: Whenever we hit the "Enter" key on the keyboard, we are actually telling the computer to insert an invisible character into our text file to indicate to the computer that there should be a new line. Unix systems adds one character called the "line feed" character or LF or \n while Windows systems adds two characters, "carriage return" and "line feed" or CRLF or \r\n.


To fix this, Windows users should set the global autocrlf attribute to true: git config --global core.autocrlf true. More information can be found here: https://help.github.com/articles/dealing-with-line-endings/#platform-all

## Comparing a commit to its parent
The command Caroline mentions to compare a commit to its parent is git show commit_id


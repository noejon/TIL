`git rebase -i HEAD~nbCommits`
Keep the first commit and replace the following `pick`s with `s`s
`:2,$s/pick/insert_what_you_would_like_to_replace_here/g`
Then modify your commit messages if necessary
Once the rebase is successful run `git push -f`

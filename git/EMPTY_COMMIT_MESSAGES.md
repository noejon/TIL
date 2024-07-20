# Empty commit messages

Days where I wrote a commit message such as "just trying something" or "X" are over...

More often than not I now create a proper commit message when squash and merging directly from github (deleting all the "trying" and "X" messages).

Today I saw this [amazing article](https://schpet.com/note/git-commit-messages-are-optional) so decided to add it to TIL.

So it turns out there is a [flag for this](https://git-scm.com/docs/git-commit#Documentation/git-commit.txt---allow-empty-message) - `--allow-empty-message`

I checked that it was not in the [default aliases from oh-my-zsh](https://kapeli.com/cheat_sheets/Oh-My-Zsh_Git.docset/Contents/Resources/Documents/index) and then also aliased it

```git
git config --global alias.empty 'commit --allow-empty-message -m ""'
```

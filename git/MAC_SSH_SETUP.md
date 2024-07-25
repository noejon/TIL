# Setting up SSH on newest Mac OS

Since I have my new machine, I needed to `ssh-add` every time my machine was going to sleep, otherwise pushes would not work.

In the past I came up with a solution that was working but was somewhat ugly, I would just add the `ssh-add` in my `.zshrc` file so that it loads each time I open a new terminal.

This time I had a look if there was something better and stumbled upon this [apple stack exchange entry](https://apple.stackexchange.com/questions/48502/how-can-i-permanently-add-my-ssh-private-key-to-keychain-so-it-is-automatically/250572#250572)

Here are the steps outlined in there:

## Store the passphrase in the keychain

```zsh
ssh-add --apple-use-keychain ~/.ssh/<private-key>
```

## Add it to the `.ssh/config` file

Go to the `.ssh` folder.

```zsh
cd ~/.ssh
```

check if the config file is present

```zsh
ls -l | grep config
```

If nothing is shown in your terminal the file is missing so it needs to be created

```zsh
touch config
```

Then the following information needs to be added to the file:

```text
Host *
    UseKeychain yes
    AddKeysToAgent yes
    IdentityFile ~/.ssh/<private-key>
```

`UseKeychain yes` is what tells `ssh` to look in your OSX keychain for the key passphrase.

## Make sure it works

- Turn the machine off or make it sleep by singing a nice lullaby to it.
- Turn the machine back on or gently wake it up by petting it on the back.
- Make a change to a file that you need to push to github
- `git push` should hopefully not throw an error

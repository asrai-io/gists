# Managing your git credentials

## Change commit name and email

```console
> git config --global user.name name
> git config --global user.email name@domain.com

> git config --global --get user.name
> git config --global --get user.email
```

## Dealing with multiple accounts (more to follow...)

__For git bash on windows:__
Upgrade the installation and don't use the windows credential manager, this will install a hook into git push, pull, ...

__macos:__
See: <https://github.com/microsoft/Git-Credential-Manager-Core>

__macos__:
erase git credentials

<https://stackoverflow.com/questions/11067818/how-do-you-reset-the-stored-credentials-in-git-credential-osxkeychain>

__NOTE:__:
press enter after entering the first command, then type the next lines, pressing enter afterwards
and twice at the end

```shell
sudo git credential-osxkeychain erase
host=github.com
protocol=https
 ⏎
 ⏎
```

```console
> brew tap microsoft/git
> brew install --cask git-credential-manager-core
```

- logout from the browser session
- delete the current account using the command line

```console
> git credential-manager delete https://github.com
> git push # triggers prompt for login
```

- select browser login

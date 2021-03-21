# Managing your git credentials

## Change commit name and email

```console
> git config --global user.name name
> git config --global user.email name@domain.com

> git config --global --get user.name
> git config --global --get user.email
```

## Dealing with multiple accounts (more to follow...)

(For git bash on windows, upgrade the installation and don't use the windows credential manager)

- logout from the browser session
- delete the current account using the command line

```console
> git credential-manager delete https://github.com
> git push # triggers prompt for login
```

- select browser login

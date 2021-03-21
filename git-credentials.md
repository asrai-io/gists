# Change commit name and email

```console
> git config --global user.name name
> git config --global user.email name@domain.com

> git config --global --get user.name
>% git config --global --get user.email
```

## dealing with multiple accounts (more to follow...)

- logout from the browser session
- delete the current account using trhe command line
- push
- select browser login

```console
> git credential-manager delete https://github.com
```

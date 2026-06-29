One can use ghswap installed by:
```bash
pnpm install -g ghswap
```

## OR

To add an account, we can just:
```bash
gh auth login
```

then can switch accounts using `gh auth switch --user kpnc0`

Add this to ~/.bashrc

```bash
alias gh-kpnc='gh auth switch --user kpnc0 && git config --global user.name "kpnc0" && git config --global user.email "kpnc0@email.com"'
alias gh-xpz4='gh auth switch --user XPZ4Y && git config --global user.name "XPZ4Y" && git config --global user.email "xpz4y@email.com"'
```

I will soon learn about ssh keys

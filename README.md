Add the following to the `.bashrc`:

```
function _update_ps1() {
    PS1="$(/usr/bin/powerline-go -colorize-hostname -hostname-only-if-ssh -cwd-max-depth 3 -git-mode simple -modules host,cwd,git,exit -theme ~/.config/powerline-go/breeze.json -error $? -jobs $(jobs -p | wc -l))"
}

if [ "$TERM" != "linux" ] && [ -f "/usr/bin/powerline-go" ]; then
    PROMPT_COMMAND="_update_ps1; $PROMPT_COMMAND"
fi
```

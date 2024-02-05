# Windows
Get: 
- VSCode
- Git Bash (comes with git)
- Github Desktop
- Miniconda (I main python)
- Docker Desktop

## Git Bash modifications
### Command Prompt customisation 
showing:
```
[Wed 24-01-2024 00:49:33] <name>@<name-device> ~ > 
```

- edit `~/.bashrc`
    ```
    # timestamp
    export PS1="[\D{%a %d-%m-%Y %T}] \u@\h \w > "
    ```

### Git (config) setup
read [1.6 Getting Started - First-Time Git Setup](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)

- name: 
    ```
    git config --global user.name "<name-device>"
    ```

- email
    ```
    git config --global user.email <email>
    ```

- default branch name (main)
    ```
    git config --global init.defaultBranch main
    ```

- default editor (set vscode)
    ```
    git config --global core.editor "'<path to vscode>' --wait"
    ```

- chaeck settings
    ```
    git config --list
    ```

### copy and paste 
remember:

paste in git bash is -> `shift` + `inv`

## VSCode modifications
add middle ruler: 
- `control` + `shift` + `p`
- enter `user settings (JSON)`
- add: 
    ```
    "editor.rulers": [
        80
    ],
    ```

set bash as default: 
- can set in UI
- or edit in `settings.json`:
    ```
    "terminal.integrated.shell.windows": < path to bash.exe >
    ```

set conda base python as default python interpreter:
- edit in `settings.json`:
    ```
    "python.pythonPath": < path to conda python, may look like "/c/Users/<name>/miniconda3/python3.exe" >,
    "python.defaultInterpreterPath": < path to conda python, may look like "/c/Users/<name>/miniconda3/python3.exe" >,
    ```


## Conda
Add into `.bash_profile`: 
```
# >>> conda initialize >>>
# !! Contents within this block are managed by 'conda init' !!
eval "$('/c/Users/<user name>/miniconda3/Scripts/conda.exe' 'shell.bash' 'hook')"
# <<< conda initialize <<<
```
Check if `.condarc`:
```
channels:
  - defaults
ssl_verify: true
auto_activate_base: true

```

## bashrc & bash_profile
Add into `.bashrc`: 
```
# Source global definitions
if [ -f /etc/bashrc ]; then
    . /etc/bashrc
fi
```
Add into `.bash_profile`: 
```
# Get the aliases and functions
if [ -f ~/.bashrc ]; then
        . ~/.bashrc
fi
```
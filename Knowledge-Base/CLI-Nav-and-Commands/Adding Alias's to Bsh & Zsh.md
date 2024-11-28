# Zsh and Bash Aliases Cheat Sheet

## 1. Adding Aliases to Zsh or Bash
Aliases are shortcuts for commands to save time and reduce repetitive typing.

### Adding Aliases
1. Open the shell configuration file:
   - **Zsh**: `~/.zshrc`
   - **Bash**: `~/.bashrc`

2. Add an alias:
   ```bash
   alias <shortcut_name>='<command>'
   ```
   Example:
   ```bash
   alias ll='ls -la'
   alias ghrepos='cd /mnt/d/OneDrive/GH_Repositories'
   ```

3. Save the file and reload the shell configuration:
   ```bash
   source ~/.zshrc   # For Zsh
   source ~/.bashrc  # For Bash
   ```

4. Use your alias in the terminal:
   ```bash
   ll
   ghrepos
   ```

---

## 2. Listing Aliases
### View All Defined Aliases
Run:
```bash
alias
```

### Find a Specific Alias
Use `grep` to filter aliases by keyword:
```bash
alias | grep <keyword>
```
Example:
```bash
alias | grep gh
```

---

## 3. Removing an Alias (Temporary)
Remove an alias for the current session:
```bash
unalias <shortcut_name>
```
Example:
```bash
unalias ll
```

> **Note**: This does not remove the alias permanently. To permanently delete it, remove the alias line from `~/.zshrc` or `~/.bashrc` and reload the configuration.

---

## 4. Examples of Common Aliases
Here are some useful aliases to get started:

### Navigation
```bash
alias ..='cd ..'
alias ...='cd ../..'
alias docs='cd ~/Documents'
alias ghrepos='cd /mnt/d/OneDrive/GH_Repositories'
```

### Listing Files
```bash
alias ls='ls --color=auto'  # Enable colored output
alias ll='ls -la'          # Long format with hidden files
alias lt='ls -lt'          # Sorted by modification time
```

### Git Shortcuts
```bash
alias gst='git status'
alias gpl='git pull'
alias gps='git push'
alias gco='git checkout'
```

### Docker Shortcuts
```bash
alias dps='docker ps'
alias dstart='docker start'
alias dstop='docker stop'
alias dexec='docker exec -it'
```

---

## 5. Advanced: Dynamic Aliases
For aliases requiring dynamic arguments, use a **function** instead:

### Example Dynamic Command:
```bash
function cdl() {
    cd "$1" && ls
}
```
- Add this to `~/.zshrc` or `~/.bashrc`.
- Usage:
  ```bash
  cdl /path/to/directory
  ```

---

## 6. Reloading Configuration
After editing aliases, reload the shell configuration file to apply changes:
```bash
source ~/.zshrc   # For Zsh
source ~/.bashrc  # For Bash
```

---

## Quick Reference
| Action                    | Command                                   |
|---------------------------|-------------------------------------------|
| **Add an Alias**          | `alias <shortcut_name>='<command>'`      |
| **List Aliases**          | `alias`                                  |
| **Search for an Alias**   | `alias | grep <keyword>`                 |
| **Remove an Alias**       | `unalias <shortcut_name>`                |
| **Reload Configuration**  | `source ~/.zshrc` or `source ~/.bashrc`  |

---

## Bonus: Add Aliases for Reloading Shell Configuration
### Zsh
```bash
alias reload='source ~/.zshrc'
```

### Bash
```bash
alias reload='source ~/.bashrc'
```

---

## Example Aliases File
Here’s how your `~/.zshrc` or `~/.bashrc` might look:
```bash
# Navigation Aliases
alias ..='cd ..'
alias docs='cd ~/Documents'

# File Management
alias ll='ls -la'
alias lt='ls -lt'

# Git Shortcuts
alias gst='git status'
alias gpl='git pull'
alias gps='git push'

# Reload Shell Config
alias reload='source ~/.zshrc'  # Replace with ~/.bashrc for Bash
```


This cheat sheet provides comprehensive instructions while remaining concise and actionable.

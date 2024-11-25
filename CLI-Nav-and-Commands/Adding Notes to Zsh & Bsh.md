# Zsh Notes and Toggles Cheat Sheet

## 1. Custom Function for Quick Notes
Add categorized notes directly in `.zshrc`.

### Example `.zshrc` Function
```bash
function mynotes() {
    case $1 in
        docker)
            echo "Docker Commands:"
            echo "  docker ps        # List running containers"
            echo "  docker build .   # Build image from Dockerfile"
            ;;
        git)
            echo "Git Commands:"
            echo "  git status       # Check the current status"
            echo "  git push         # Push changes to the repository"
            ;;
        *)
            echo "Available categories: docker, git"
            ;;
    esac
}
```

### Usage
```bash
mynotes docker
mynotes git
```

---

## 2. Notes in a Central Text File
Store notes in a file and search by category.

### Create Notes File
Save notes in `~/command_notes.txt`:
```
[Docker]
docker ps        - List running containers
docker exec ...  - Access container shell

[Git]
git status       - Check current status
git log          - View commit history
```

### Add a Search Function
Add this to `.zshrc`:
```bash
function mynotes() {
    grep -A 10 "\[$1\]" ~/command_notes.txt || echo "Category not found. Available categories are:"
    grep -o "\[.*\]" ~/command_notes.txt | tr -d '[]'
}
```

### Usage
```bash
mynotes Docker
mynotes Git
```

---

## 3. Environment Variable Toggles
Use toggles for settings or flags.

### Add Toggles in `.zshrc`
```bash
export SHOW_DOCKER_INFO=true
export ENABLE_VERBOSE_LOGGING=false
```

### Create a Function to Check Toggles
```bash
function checktoggles() {
    echo "Docker Info: $SHOW_DOCKER_INFO"
    echo "Verbose Logging: $ENABLE_VERBOSE_LOGGING"
}
```

### Usage
```bash
checktoggles
export SHOW_DOCKER_INFO=false
```

---

## 4. Directory-Based Notes
Store notes in individual files by category.

### Setup
1. Create a directory:
   ```bash
   mkdir ~/notes
   ```

2. Add files for each category:
   ```bash
   echo "docker ps - List running containers" > ~/notes/docker.txt
   echo "git status - Check current status" > ~/notes/git.txt
   ```

3. Add a Function in `.zshrc`:
   ```bash
   function mynotes() {
       local note_file=~/notes/$1.txt
       if [[ -f $note_file ]]; then
           cat $note_file
       else
           echo "Note not found. Available categories:"
           ls ~/notes | sed 's/\.txt$//'
       fi
   }
   ```

### Usage
```bash
mynotes docker
mynotes git
```

---

## Quick Reference for Notes & Toggles
| Feature                  | Command/Description                                 |
|--------------------------|-----------------------------------------------------|
| **Custom Notes**         | `mynotes <category>`                                |
| **Central Notes File**   | Notes in `~/command_notes.txt`, search with `mynotes <category>` |
| **Environment Toggles**  | `checktoggles` to view, `export VAR=value` to update |
| **Directory Notes**      | Notes in `~/notes/<category>.txt`, use `mynotes <category>` |

---

## Bonus: Reload Zsh Configuration
After updates to `.zshrc`, reload with:
```bash
source ~/.zshrc
```

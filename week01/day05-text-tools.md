# Day 5: Linux Text Processing & Stream Tools (`grep`, `find`, Pipes, and Redirects)

## 1. Overview of Today's Concepts

Today focused on mastering command-line text filters and stream manipulation in Linux, allowing us to search logs, locate files across directories, and chain commands together efficiently.

---

## 2. Three Useful One-Liners

### A. Searching Inside Files with `grep`

- **Command:** `grep -i "error" /var/log/syslog`
- **What it does:** Searches for the keyword `"error"` (case-insensitive due to `-i`) inside the system log file. Essential for troubleshooting failed services.

### B. Finding Files by Name with `find`

- **Command:** `find . -name "*.conf" -type f`
- **What it does:** Recursively searches the current directory (`.`) for all files (`-type f`) ending with the extension `.conf`.

### C. Chaining Commands with Pipes (`|`) and Saving Output (`>`)

- **Command:** `history | grep "git" > git-commands.txt`
- **What it does:** Takes your command history, filters out lines containing `"git"` using a pipe (`|`), and writes (`>`) the filtered results directly into a new text file.

---

## 3. Key Operators Explained

- **Pipe (`|`):** Sends the output of the command on the left as the input to the command on the right.
- **Redirect (`>`):** Overwrites output into a file.
- **Append (`>>`):** Adds output to the end of an existing file without overwriting it.

📄 Linux Text Editors

## 1️⃣ What is a Linux Text Editor?

A Linux text editor is a tool used to create, modify, and manage text files (such as config files, scripts, and plain text) on Linux.

There are many editors, but two popular ones are:
- **Vim** → advanced, powerful, steeper learning curve
- **Nano** → simple, user-friendly, great for beginners

---
<img width="902" alt="Image" src="https://github.com/user-attachments/assets/bab02001-0774-4cc9-aa4f-be7bc79b344f" />
## 2️⃣ Vim (Vi Improved)

### 📥 Open a file (create if not exists)
```bash
vim exercise.txt
```

### ✏️ Enter Insert Mode
- Press `i`

### 📝 Type in the file
```
Hello, this is a Vim hands-on project.
Welcome to darey.io.
```

### 🔀 Navigate
- Arrow keys or
- `h` (left), `j` (down), `k` (up), `l` (right)

### ❌ Delete
- Character → `x` (in normal mode)
- Line → `dd`

### ↩️ Undo
- Press `u`

### 💾 Save and Quit
- `:wq` → write and quit

### 🚪 Quit Without Saving
- `:q!` → quit without saving
---
<img width="959" alt="Image" src="https://github.com/user-attachments/assets/66bb41f2-d1cd-46e7-9bc7-361f4ad6b4de" />
## 3️⃣ Nano

### 📥 Open a file
```bash
nano nano_file.txt
```

### 📝 Enter and Edit Text
- Just start typing!

### 💾 Save Changes
- Press `Ctrl + O`
- Confirm filename → press Enter

### 🚪 Exit
- Press `Ctrl + X`

### 📂 Open Existing File
```bash
nano existing_file.txt
```

---
<img width="929" alt="Image" src="https://github.com/user-attachments/assets/856422b7-3c2c-4f77-a145-ea7f04c26881" />
## 🗂️ Cheat Sheet

| Action               | Vim Command            | Nano Command         |
|----------------------|------------------------|----------------------|
| Open file           | `vim filename`         | `nano filename`      |
| Enter insert mode   | `i`                   | (start typing)       |
| Navigate           | `h`/`j`/`k`/`l` or arrows | arrows              |
| Delete character    | `x`                   | `Ctrl + D`           |
| Delete line         | `dd`                  | `Ctrl + K`           |
| Undo               | `u`                   | `Ctrl + U`           |
| Save changes        | `:w` or `:wq`         | `Ctrl + O` → Enter   |
| Quit without saving | `:q!`                 | `Ctrl + X` (then N)  |
| Exit editor         | `:q` or `:wq`         | `Ctrl + X`           |

---

⭐ **Tip:** Vim is modal → you must exit insert mode (with `Esc`) to run commands. Nano is straightforward but has fewer advanced features.

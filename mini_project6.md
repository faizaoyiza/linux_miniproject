
# Shell Scripting Tutorial

## Introduction

With thousands of commands available to the command line user, how can we remember them all? The answer is, we don't. The real power of the computer is its ability to do the work for us. To get it to do that, we use the power of the shell to automate things. We write shell scripts.

## What is Shell Scripting?

Imagine you're tasked with setting up new workstations and user accounts regularly at your job. Instead of manually creating each folder and user account, a simple shell script serves as your efficient digital helper. By automating the creation of multiple directories and user accounts with just a few lines of code, it saves you considerable time and effort, allowing you to concentrate on more critical aspects of your work.

Shell scripting is the process of writing and executing a series of instructions in a shell to automate tasks. A shell script is essentially a script or program written in a shell language, such as Bash, sh, zsh, or PowerShell.

---

## Task

### Step 1: Create a folder on the Ubuntu server named `shell-scripting`

```bash
mkdir shell-scripting
```

### Step 2: Change into the folder

```bash
cd shell-scripting
```

### Step 3: Create a shell script file using `vim`

```bash
vim my_first_shell_script.sh
```
### Step 4: Add the following shell script code into the file

```bash
#!/bin/bash

# Create 3 folders
mkdir folder1 folder2 folder3

# Create 3 users
sudo adduser --disabled-password --gecos "" user1
sudo adduser --disabled-password --gecos "" user2
sudo adduser --disabled-password --gecos "" user3
```
<img width="959" alt="Image" src="https://github.com/user-attachments/assets/f65fadb4-471c-4140-9e16-92de8f794704" />
### Step 5: Save and exit the file  
- Press `Esc`  
- Type `:wq`  
- Press `Enter`

### Step 6: Confirm the file exists

```bash
ls -latr
```

You should see the file `my_first_shell_script.sh` with permissions like `-rw-r--r--`.
<img width="955" alt="Image" src="https://github.com/user-attachments/assets/9a27e35d-26d8-476c-a628-4f53c2664929" />
### Step 7: Add execute permission for the owner

```bash
chmod u+x my_first_shell_script.sh
```

### Step 8: Run the script

```bash
./my_first_shell_script.sh
```

### Step 9: Confirm that the folders were created

```bash
ls -l
```

You should see:

```
folder1  folder2  folder3
```

### Step 10: Confirm that the users were created

```bash
id user1
id user2
id user3
```

Each should return output like:

```
uid=1001(user1) gid=1001(user1) groups=1001(user1)
```

---
<img width="625" alt="Image" src="https://github.com/user-attachments/assets/65ecb58b-fcda-4b5a-8877-5a4d20af21bc" />
## Explanation

- The **shebang** `#!/bin/bash` tells the system to use the Bash shell interpreter to run the script.
- `mkdir` creates directories.
- `adduser` creates users without setting a password (disabled password).
- `chmod u+x` adds execute permission for the file owner.
- Running the script with `./` tells the shell to look for the script in the current directory.

---

## What is a Shebang?

The first line `#!/bin/bash` is called a **shebang**. It specifies the interpreter to be used to execute the script. Here, it points to the Bash shell located at `/bin/bash`.

Without a shebang, the system might not know how to execute the script, and you would have to specify the interpreter manually.

---


# Control Flow in Shell Scripting

Control flow statements are the backbone of making decisions in programming. In scripting, these statements let your scripts decide what to do or how to proceed based on conditions, loops, or user inputs.

Bash and other shell interpreters provide control flow statements like:

- `if-else`
- `for` loops
- `while` loops
- `case` statements

We'll focus on the most common ones at this level: `if-else` and `for` loops.

## What is Control Flow?

Control flow directs the order in which commands or instructions are executed in a script.

---

## If-Else Statement

A basic example:

```bash
#!/bin/bash

read -p "Enter a number: " num

if [ $num -gt 0 ]; then
  echo "The number is positive."
elif [ $num -lt 0 ]; then
  echo "The number is negative."
else
  echo "The number is zero."
fi
```

### Breakdown:

- `#!/bin/bash`: Shebang line to specify Bash interpreter.
- `read -p`: Prompts user for input and stores in `num`.
- `if`, `elif`, `else`, `fi`: Conditional logic blocks.
- Operators: `-gt` (greater than), `-lt` (less than).

---

## Loops

Loops allow repeating a set of instructions multiple times.

### Real-world scenarios:

- **Batch Processing** (e.g. resizing photos)
- **Data Analysis**
- **Automated Testing**

### Types of Loops in Bash

1. `for`
2. `while`
3. `until`

### For Loop (List Form)

```bash
#!/bin/bash

for i in 1 2 3 4 5
do
  echo "Hello, World! This is message $i"
done
```

### For Loop (Range Form)

```bash
#!/bin/bash

for i in {1..5}
do
  echo "Counting... $i"
done
```

### Task for You:

- Create shell scripts for each form of the for loop.
- Insert the code into `.sh` files.
- Set executable permissions using `chmod +x filename.sh`
- Execute and evaluate your results.

# Bash Loop Examples

This project demonstrates two types of `for` loops in Bash scripting:  
- **List-style for loop**  
- **C-style for loop**

Each loop is written in its own script, with proper execution permissions and runnable from the command line.

---

## 🛠️ Step-by-Step Instructions

### 1. Create the Project Directory

bash
mkdir bash-loops
cd bash-loops

### 2. Create the List-Style For Loop Script
nano for_loop_list.sh

#!/bin/bash

# This is a list-style for loop
for item in Apple Banana Mango Orange; do
  echo "I like $item"
done
### 3. Create the C-Style For Loop Script
nano for_loop_c_style.sh
#!/bin/bash

# This is a C-style for loop
for ((i=1; i<=5; i++)); do
  echo "Number $i"
done
### 4.  Make Both Scripts Executable
chmod +x for_loop_list.sh
chmod +x for_loop_c_style.sh
### 5. Run the Scripts
./for_loop_list.sh
./for_loop_c_style.sh

<img width="959" alt="Image" src="https://github.com/user-attachments/assets/266dab30-416a-4a0a-ae59-36fc5f048b8d" />
## 📁 Folder Structure



## C-Style For Loop

```bash
#!/bin/bash

for (( i=0; i<5; i++ ))
do
  echo "Number $i"
done
```

### Breakdown

- Initialization: `i=0`
- Condition: `i<5`
- Increment: `i++`
- Executes commands within `do` ... `done`

---

Use loops and conditionals to automate and simplify your scripts.

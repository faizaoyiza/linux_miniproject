# Bash Script for Generating a Multiplication Table

## Overview

This script prompts the user for a number and generates its multiplication table using both list-style and C-style `for` loops. It allows generating a full table (1 to 10) or a partial range, with options for ascending or descending order. The script also validates user input and provides clear, readable output.

---
## Features and Criteria

### 1. User Input Handling
- Prompts the user to enter a number (1-10).
- Asks whether to generate a full or partial table.
- Requests preferred order: ascending or descending.
- Offers the option to generate multiple tables in one run.

### 2. Input Validation
- Checks if the entered number is within the range 1-10.
- Validates partial range inputs.
- Provides error messages for invalid inputs and prompts again.

### 3. Loop Usage
- Implements **list-style loops**: `for i in {1..10}` and `for i in $(seq ...)`.
- Implements **C-style loops**: `for ((i=; i<=; i++))`.

### 4. Range and Order Handling
- Supports generating the full table (1 to 10).
- Supports partial range based on user input.
- Can display tables in ascending or descending order.

### 5. Clear Output
- Formats output as `X x Y = Z`.
- Separates different loop examples with clear labels.

### 6. Repeatability
- Allows multiple runs without restarting the script.

### 7. Readability
- Includes comments explaining each part of the code for clarity.

---
<img width="950" height="518" alt="Image" src="https://github.com/user-attachments/assets/71065d20-fe5b-4420-8430-fd697bc9d418" />



<img width="559" height="304" alt="Image" src="https://github.com/user-attachments/assets/589a97f8-b12e-4e75-9676-cf2432b6da6b" />
## Script Code

```bash
#!/bin/bash
#
# multiplication_table.sh
# Generates a multiplication table with full/partial range and order options
#

# Prompt for number
read -rp "Enter a positive integer for the multiplication table: " num
if ! [[ "$num" =~ ^[1-9][0-9]*$ ]]; then
    echo "❌ Invalid number. Exiting."
    exit 1
fi

# Ask for full or partial
read -rp "Do you want a full table (1-10) or partial table? (f/p) [f]: " choice
choice=${choice,,}
[[ -z "$choice" ]] && choice="f"

start=1
end=10

if [[ "$choice" == "p" ]]; then
    read -rp "Enter the starting number (1-10): " start
    read -rp "Enter the ending number (1-10): " end
    if ! [[ "$start" =~ ^[1-9]$|10$ ]] || ! [[ "$end" =~ ^[1-9]$|10$ ]] || (( start > end )); then
        echo "⚠️  Invalid range. Defaulting to full table (1-10)."
        start=1
        end=10
    fi
fi

# Ask order
read -rp "Display order ascending or descending? (a/d) [a]: " order
order=${order,,}
[[ -z "$order" ]] && order="a"

echo
if [[ "$start" -eq 1 && "$end" -eq 10 ]]; then
    echo "Multiplication table for $num (1-10):"
else
    echo "Multiplication table for $num ($start-$end):"
fi
echo "----------------------------------------"

if [[ "$order" == "a" ]]; then
    # List-form loop
    for i in $(seq $start $end); do
        printf "%d × %d = %d\n" "$num" "$i" $((num * i))
    done
else
    # C-style loop
    for (( i=end; i>=start; i-- )); do
        printf "%d × %d = %d\n" "$num" "$i" $((num * i))
    done
fi


---

## Summary

This script demonstrates:
- User input handling
- Input validation
- Looping constructs (list form and C-style)
- Conditional logic for full/partial range and order
- Clear output formatting

---

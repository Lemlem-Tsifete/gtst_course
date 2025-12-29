
# Linux Text Processing Cheat Sheet

This repository contains essential commands for searching, editing, and processing text files in Linux using `grep`, `sed`, and `awk`.

## 1. Grep (Global Regular Expression Print)

Used for searching text patterns within files.

|**Command**|**Description**|
|---|---|
|`grep -i "pattern" file`|**Case-insensitive** search (ignores upper/lower case).|
|`grep -c "pattern" file`|**Count** the number of lines that match the pattern.|
|`grep -l "pattern" *`|**List** only the names of files containing the pattern.|
|`grep -r "pattern" dir/`|**Recursive** search through all files in a directory.|
|`grep -o "pattern" file`|**Only** show the matched string, not the whole line.|
|`grep -w "pattern" file`|Match the **whole word** only (e.g., avoids matching `inet6` when searching for `inet`).|

---

## 2. Sed (Stream Editor)

A powerful tool for parsing and transforming text line-by-line.

### Basic Syntax

`sed 's/old_text/new_text/' filename`

### Common Operations

- **Substitute (First Instance):** Change only the first occurrence in a line.
    
    Bash
    
    ```
    sed 's/old/new/' file.txt
    ```
    
- **Global Substitute:** Change every occurrence in the file.
    
    Bash
    
    ```
    sed 's/old/new/g' file.txt
    ```
    
- **Delete Lines:** Remove lines containing a specific pattern.
    
    Bash
    
    ```
    sed '/pattern/d' file.txt
    ```
    

---

## 3. AWK

Best for processing **structured data** (columns and rows), such as CSV or log files.

**Syntax:** `awk 'pattern { action }' file`

- **Example:** To print the first column of a file:
    
    Bash
    
    ```
    awk '{print $1}' file.txt
    ```
    

---

## 4. File Information & Logic

### Word Count (`wc`)

Used to count lines, words, and characters.

Bash

```
wc file.txt
```

### Multiple Command Execution

|**Operator**|**Logic**|**Description**|
|---|---|---|
|`;`|**Sequential**|Runs commands one after another regardless of success.|
|`&&`|**AND**|Runs the second command only if the first succeeds.|
|`\|`|**OR**|Runs the second command only if the first fails.|
|`\|`|**Pipe**|Passes the output of one command as input to the next.|
# Linux part-1 [tryhackme]

**Linux Terminal Basics - TryHackMe Notes**

---

### 🔢 Why Terminal Matters

- Lightweight OSs (like Ubuntu) often lack GUI.
- Terminal provides full control via text commands.

---

### ⚙️ Basic Terminal Structure

```
tryhackme@linux1:~$ <enter commands here>

```

---

### ✉️ Essential Commands

| Command | Description | Example |
| --- | --- | --- |
| `echo` | Outputs text | `echo "Hello Friend!"` |
| `whoami` | Displays current logged-in user | `whoami` |
| `ls` | Lists files/folders in current directory | `ls` or `ls Pictures` |
| `cd` | Changes directory | `cd Documents` |
| `cat` | Outputs contents of files | `cat todo.txt` |
| `pwd` | Prints full path of current directory | `pwd` |

---

### 📁 Navigating the Filesystem

- **List Directory Content:**
    
    ```bash
    ls
    ls Pictures
    
    ```
    
- **Change Directory:**
    
    ```bash
    cd Pictures
    
    ```
    
- **Show Current Location:**
    
    ```bash
    pwd
    # Example output: /home/ubuntu/Pictures
    
    ```
    

---

### 📄 Working with Files

- **View Contents:**
    
    ```bash
    cat todo.txt
    cat /home/ubuntu/Documents/todo.txt
    
    ```
    

---

### ✨ Pro Tips

- Use `ls <dir>` and `cat <file>` without changing into them.
- Remember quotes for echoing multi-word strings: `echo "Hello world"`
- Use `pwd` if you lose track of your current path.

---

### 

# 

---

## 🔍 Using `find`

`find` helps locate files efficiently, instead of manually checking folders with `cd` and `ls`.

### 🔹 Basic Usage

- **Find a specific file**:
    
    ```bash
    find -name filename.txt
    
    ```
    
    > Searches from current directory down for the exact file.
    > 
- **Find files by extension**:
    
    ```bash
    find -name "*.txt"
    
    ```
    
    > Wildcard * matches all files ending in .txt.
    > 

### 🧠 Example:

```bash
$ find -name passwords.txt
./folder1/passwords.txt

$ find -name "*.txt"
./folder1/passwords.txt
./Documents/todo.txt

```

---

## 📂 Using `grep`

`grep` lets you search **inside** files for specific text patterns.

### 🔹 Basic Usage

- **Search for text inside a file**:
    
    ```bash
    grep "pattern" filename
    
    ```
    
    > Returns lines where the pattern is found.
    > 

### 🧠 Example:

```bash
$ wc -l access.log
244 access.log

$ grep "81.143.211.90" access.log
81.143.211.90 - - [25/Mar/2021:11:17 +0000] "GET / HTTP/1.1" 200 417 a...

```

---

## ⚙️ Linux Shell Operators

Operators increase efficiency by combining or redirecting commands.

### 🔸 `&` — Run in Background

```bash
long_running_command &

```

> Runs the command in the background.
> 

---

### 🔸 `&&` — Run Next Command If Previous Succeeds

```bash
command1 && command2

```

> Only runs command2 if command1 was successful.
> 

---

### 🔸 `>` — Redirect Output (Overwrite)

```bash
echo "hello" > file.txt

```

> Creates/overwrites file with "hello".
> 

---

### 🔸 `>>` — Redirect Output (Append)

```bash
echo "again" >> file.txt

```

> Appends "again" at the end of file.txt.
> 

### 🧠 Example:

```bash
$ echo hey > welcome
$ cat welcome
hey

$ echo hello >> welcome
$ cat welcome
hey
hello

```

---

## ✅ Summary

- `find` = Locate files
- `grep` = Search **inside** files
- `&` = Background process
- `&&` = Chain commands
- `>` = Overwrite file
- `>>` = Append to file

Great for working efficiently in Linux without unnecessary navigation or repetition.
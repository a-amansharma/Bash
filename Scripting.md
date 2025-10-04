# 🧾 Bash Syntax – The Basics

**Start of a script:**
```bash
#!/bin/bash
```

**Basic Syntax Rules:**
- Use `#` for comments
- Each command is on a new line
- Scripts must be made executable: `chmod +x script.sh`

**Example:**
```bash
#!/bin/bash
echo "Hello, Bash!"
```
Run with:
```bash
./script.sh
```

---

# 📜 Bash Script – Writing Your First Script

**Steps:**
1. Create file: `nano hello.sh`
2. Add:
```bash
#!/bin/bash
echo "Hello World"
```
3. Make executable: `chmod +x hello.sh`
4. Run: `./hello.sh`

**Multiline Example:**
```bash
#!/bin/bash
name="Kashif"
echo "Welcome, $name"
date
```

---

# 🔡 Bash Variables – Store and Use Data

**Declare:**
```bash
name="Kashif"
```

**Access:**
```bash
echo $name
```

**Rules:**
- No spaces around `=`
- Use `$` to reference value

**Example:**
```bash
#!/bin/bash
user="kashif"
echo "Welcome $user"
```

---

# 🗂️ Bash Data Types (Implicit)

Bash supports:

- **Strings** (default type)
- **Integers** (with `let` or `$(( ))`)
- **Arrays** (indexed)

**Examples:**
```bash
name="Kashif"        # String
age=20             # Integer

let age=age+1
echo $age

arr=(one two three)  # Array
echo ${arr[0]}
```

---

# ➕ Bash Operators

### Arithmetic:
```bash
a=5
b=3
echo $((a + b))
```

### Comparison:
| Operator | Description       |
|----------|-------------------|
| `-eq`    | Equal              |
| `-ne`    | Not equal          |
| `-gt`    | Greater than       |
| `-lt`    | Less than          |
| `-ge`    | Greater or equal   |
| `-le`    | Less or equal      |

**Example:**
```bash
if [ $a -gt $b ]; then
  echo "a > b"
fi
```

---

# 🔀 Bash If...Else

**Syntax:**
```bash
if [ condition ]; then
   commands
elif [ condition ]; then
   commands
else
   commands
fi
```

**Examples:**
```bash
#!/bin/bash
num=10

if [ $num -gt 5 ]; then
  echo "Greater than 5"
else
  echo "5 or less"
fi
```

---

# 🔁 Bash Loops

### `for` Loop:
```bash
for i in 1 2 3; do
  echo "Number $i"
done
```

### `while` Loop:
```bash
count=1
while [ $count -le 3 ]; do
  echo "Count is $count"
  ((count++))
done
```

### `until` Loop:
```bash
n=1
until [ $n -gt 3 ]; do
  echo "Until $n"
  ((n++))
done
```

---

# 🔣 Bash Functions

**Define:**
```bash
function_name () {
  commands
}
```

**Call:**
```bash
function_name
```

**Example:**
```bash
greet() {
  echo "Hello, $1"
}

greet "Kashif"
```

> `$1`, `$2` = arguments to the function

---

# 🧮 Bash Arrays

**Declare:**
```bash
arr=(apple banana cherry)
```

**Access:**
```bash
echo ${arr[1]}     # banana
```

**Loop through array:**
```bash
for item in "${arr[@]}"; do
  echo $item
done
```

**Array length:**
```bash
echo ${#arr[@]}
```

---

# ⏰ Bash Schedule (Cron Jobs)

**Syntax:**
```bash
* * * * * command
│ │ │ │ │
│ │ │ │ └── Day of Week (0-7)
│ │ │ └──── Month (1-12)
│ │ └────── Day of Month (1-31)
│ └──────── Hour (0-23)
└────────── Minute (0-59)
```

**Edit Crontab:**
```bash
crontab -e
```

**Example:**
```bash
0 6 * * * /home/user/backup.sh
```
Runs daily at 6:00 AM.

**List cron jobs:**
```bash
crontab -l
```

---

Made by Kashf Alam

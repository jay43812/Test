# Linux Shell Scripting Guide

## Table of Contents
1. [Introduction](#introduction)
2. [Basic About Shell](#basic-about-shell)
   - [What is a Linux Shell?](#what-is-a-linux-shell)
   - [How to check shell type](#how-to-check-shell-type)
   - [How to get OS information](#how-to-get-os-information)
   - [How to check how many shells installed in your OS](#how-to-check-how-many-shells-installed-in-your-os)
   - [How to switch shell on your machine](#how-to-switch-shell-on-your-machine)
3. [Basic About Shell Script](#basic-about-shell-script)
   - [What is Shell Scripting?](#what-is-shell-scripting)
   - [Common Shell Commands](#common-shell-commands)
   - [What is the Shebang Line?](#what-is-the-shebang-line)
   - [Creating First Shell Script](#creating-first-shell-script)
   - [How to Run a Shell Script?](#how-to-run-a-shell-script)
   - [What is rwx Permission?](#what-is-rwx-permission)
   - [Key Shortcuts](#key-shortcuts)
   - [How to Write Single Line and Multiline Comments?](#how-to-write-single-line-and-multiline-comments)
4. [Explain Variables](#explain-variables)
   - [What is a Variable in Shell Scripting?](#what-is-a-variable-in-shell-scripting)
   - [Declaring a Variable](#declaring-a-variable)
   - [Accessing a Variable](#accessing-a-variable)
   - [Rules for Variable Naming](#rules-for-variable-naming)
   - [How to Use a Variable in echo](#how-to-use-a-variable-in-echo)
   - [What is a Constant Variable](#what-is-a-constant-variable)
   - [System Variables](#system-variables)
   - [Variable Scope](#variable-scope)
     - [Local Variable](#local-variable)
     - [Global Variable](#global-variable)
     - [Special Variables](#special-variables)
5. [Explain Arrays](#explain-arrays)
   - [What is an Array in Shell Scripting?](#what-is-an-array-in-shell-scripting)
   - [Accessing Elements in an Array](#accessing-elements-in-an-array)
   - [Printing All Elements in an Array](#printing-all-elements-in-an-array)
   - [Getting the Length of an Array](#getting-the-length-of-an-array)
   - [Defining and Accessing an Empty Array](#defining-and-accessing-an-empty-array)
   - [Adding Values and Accessing to the Empty Array](#adding-values-and-accessing-to-the-empty-array)
   - [How to Get Specific Values from an Array](#how-to-get-specific-values-from-an-array)
   - [How to Update an Array](#how-to-update-an-array)
   - [What is a Key-Value Pair in an Array?](#what-is-a-key-value-pair-in-an-array)
   - [Defining an Associative Array](#defining-an-associative-array)
6. [Explain Strings](#explain-strings)
   - [What is a String in Shell Scripting?](#what-is-a-string-in-shell-scripting)
   - [Types of Strings in Shell](#types-of-strings-in-shell)
   - [String Operations](#string-operations)
7. [User Interaction](#user-interaction)
   - [How to Take a User Input (Basic User Input)](#how-to-take-a-user-input-basic-user-input)
   - [Taking Input on the Same Line](#taking-input-on-the-same-line)
   - [Hiding User Input (Password)](#hiding-user-input-password)
   - [Taking Multiple Inputs in One Line](#taking-multiple-inputs-in-one-line)
8. [Operations in Shell](#operations-in-shell)
   - [Arithmetic Operations](#arithmetic-operations)
   - [Comparison Operations](#comparison-operations)
   - [String Operations](#string-operations)
   - [Logical Operations](#logical-operations)
9. [Control Statements](#control-statements)
   - [if Statement](#if-statement)
   - [if-else Statement](#if-else-statement)
   - [elif Statement](#elif-statement)
   - [case Statement](#case-statement)
   - [Jump Statement](#jump-statement)
   - [Select Statement](#select-statement)
10. [Loops (Iteration)](#loops-iteration)
    - [For Loop](#for-loop)
    - [While Loop](#while-loop)
    - [Until Loop](#until-loop)
    - [Infinite Loop](#infinite-loop)
11. [What is Function](#what-is-function)
    - [How to Make a Function](#how-to-make-a-function)
    - [Function with Parameters](#function-with-parameters)
    - [Function with Return Value](#function-with-return-value)
    - [Shifting Arguments](#shifting-arguments)
12. [Other Useful Concepts](#other-useful-concepts)
    - [Redirection, Bash Variables, Sleep, Exit, Logger, Dev/Null](#redirection-bash-variables-sleep-exit-logger-dev-null)
    - [Debugging Methods](#debugging-methods)
    - [Run Scripts in the Background](#run-scripts-in-the-background)
    - [Crontab Usage](#crontab-usage)
13. [Projects in Shell Scripting](#projects-in-shell-scripting)
    - [Monitoring Free RAM Space](#monitoring-free-ram-space)
    - [Monitoring Free DISK Space and Sending an Alert Email](#monitoring-free-disk-space-and-sending-an-alert-email)
    - [Create a User and Display Information](#create-a-user-and-display-information)

---

## Introduction
This guide provides an overview of Linux shell scripting, its purpose, and how to get started with writing and executing shell scripts.

---

## Basic About Shell
### What is a Linux Shell?
A Linux shell is a command-line interface (CLI) used for interacting with the operating system. It allows users to enter commands to perform various tasks, like file management, running programs, and automating tasks through scripting.

### How to Check Shell Type
To check the type of shell you're using, you can use the following commands:

    echo $0

    echo $0: This prints the name of the current shell.

    echo $SHELL

### How to Get OS Information

    cat /etc/os-release

    or 

    uname -a

### How to Check How Many Shells Installed in Your OS

    cat /etc/shells

### How to Switch Shell on Your Machine
You can switch between different shells by using the chsh command or directly by specifying the shell you want to use. For example:

    chsh -s /bin/bash
    chsh -s /bin/zsh

    or 

    sh
    bash
    zsh

---

## Basic About Shell Script
### What is Shell Scripting?
Shell scripting is a way to automate tasks in Linux using a script written in a shell language. The shell script contains a series of commands executed by the shell interpreter.

### Common Shell Commands


#### File and Directory Management
| Command | Description |
|---------|-------------|
| `ls` | List files and directories |
| `pwd` | Print working directory (current directory) |
| `cd <directory>` | Change directory |
| `mkdir <directory>` | Create a new directory |
| `rmdir <directory>` | Remove an empty directory |
| `rm <file>` | Remove a file |
| `rm -r <directory>` | Remove a directory and its contents recursively |
| `cp <source> <destination>` | Copy a file or directory |
| `mv <source> <destination>` | Move or rename a file or directory |
| `touch <file>` | Create an empty file |

#### File Viewing & Editing
| Command | Description |
|---------|-------------|
| `cat <file>` | View file contents |
| `less <file>` | View file contents one page at a time |
| `head <file>` | Display the first 10 lines of a file |
| `tail <file>` | Display the last 10 lines of a file |
| `nano <file>` | Edit a file using the Nano editor |
| `vim <file>` | Edit a file using the Vim editor |

#### File Permissions & Ownership
| Command | Description |
|---------|-------------|
| `chmod <permissions> <file>` | Change file permissions (e.g., `chmod 755 myscript.sh`) |
| `chown <owner>:<group> <file>` | Change file owner |

#### Process Management
| Command | Description |
|---------|-------------|
| `ps` | Display running processes |
| `top` | Show system resource usage and processes |
| `kill <PID>` | Terminate a process by Process ID |
| `killall <process_name>` | Kill all processes with a given name |

#### Networking
| Command | Description |
|---------|-------------|
| `ping <host>` | Check connectivity to a host |
| `curl <URL>` | Fetch a web page or API response |
| `wget <URL>` | Download a file from a URL |
| `netstat -tulnp` | Show active network connections |

#### User Management
| Command | Description |
|---------|-------------|
| `whoami` | Show the current logged-in user |
| `who` | Show logged-in users |
| `sudo <command>` | Run a command as a superuser |
| `su <user>` | Switch to another user |

#### Disk and Storage
| Command | Description |
|---------|-------------|
| `df -h` | Show disk usage |
| `du -sh <directory>` | Show size of a directory |
| `mount / unmount` | Mount or unmount a drive |

#### Searching & Filtering
| Command | Description |
|---------|-------------|
| `grep <pattern> <file>` | Search for a pattern in a file |
| `find <directory> -name <filename>` | Find a file by name |
| `locate <filename>` | Locate a file in the system |

#### Archiving & Compression
| Command | Description |
|---------|-------------|
| `tar -cvf archive.tar <directory>` | Create a tar archive |
| `tar -xvf archive.tar` | Extract a tar archive |
| `zip -r archive.zip <directory>` | Create a zip file |
| `unzip archive.zip` | Extract a zip file |

#### System Information
| Command | Description |
|---------|-------------|
| `uname -a` | Display system information |
| `uptime` | Show system uptime |
| `free -h` | Show memory usage |
| `history` | Show command history |

#### Other Useful Commands
| Command | Description |
|---------|-------------|
| `clear` | Clear the terminal screen |
| `echo "text"` | Print text to the terminal |
| `date` | Show the current date and time |



### What is the Shebang Line?
The Shebang line (#!/bin/bash) at the top of a script specifies the interpreter to be used to execute the script. It tells the system which program should be used to run the script. For example:

    #!/bin/bash
    echo "Hello, World!"

### Creating First Shell Script
To create your first shell script:

1. Open a terminal and use a text editor like nano or vim to create a script file:
    
    ```bash
    nano my_script.sh
    vim my_script.sh
    vi my_script.sh

2. Add a simple command (By pressing I(i) key to insert mode) 
    ```bash
    echo "Hello, World!"

3. Save and exit the editor (By using ESC and then wq! to save and exit )

4. Make it executable:
    ```bash
    chmod +x my_script.sh
5. Run the script:
    ```bash
    ./my_script.sh
    bash my_script.sh
    sh my_script.sh

### How to Run a Shell Script?
There are several ways to run a shell script:


    ./script.sh         :  If the script is in the current directory and executable.
    /path/script.sh     :  Full path to the script.
    bash script.sh      :  Run the script with bash explicitly.
    sh script.sh        :  Run the script with sh.

### What is rwx Permission?
| Permission | Symbol | Description |
|------------|--------|-------------|
| Read       | `r`    | Allows viewing the content of the file |
| Write      | `w`    | Allows modifying or editing the file |
| Execute    | `x`    | Allows running the file as a program |

How to change the permission of a shell script?
To change the permissions of a shell script, use the chmod command:

    chmod +x script.sh   # Adds execute permission
    chmod u+x script.sh  # Adds execute permission to the user
    chmod 755 script.sh  # Sets read, write, execute for user and read, execute for others

### Key Shortcuts

    Ctrl + C    : Terminates the running process.
    Ctrl + Z    : Suspends the current process.


### How to Write Single Line and Multiline Comments?

    Single-line comment     :   Begin with a #
    # This is a single-line comment 

    Multiline comment: Use  :   'comment' or simply use multiple # lines:

    : '
    This is a multiline
    comment in a shell script.
    '
---

## Explain Variables
### What is a Variable in Shell Scripting?
A **variable** in shell scripting is a placeholder for storing data such as strings, numbers, or command outputs. Variables help in reusing values, making scripts more dynamic and flexible.


| Variable Type      | Description |
|--------------------|-------------|
| **Local Variable** | Available only within the current shell session or script. Not accessible by child processes. |
| **Environment (Global) Variable** | Available across all shell sessions and inherited by child processes. Defined using `export`. |
| **Special Variable** | Predefined by the shell and provides system-related information, such as script name, arguments, process ID, etc. |

### Declaring a Variable
In shell scripting, variables are assigned without any data type.

#### Example:
   
    name="Alice"
    age=25

### Accessing a Variable
To access a variable, use the `$` symbol before the variable name.

### Example:

    echo "My name is $name and I am $age years old."

    My name is Alice and I am 25 years old.

### Rules for Variable Naming
1.  A variable name can contain letters, numbers, and underscores (_).
2.  A variable name must not start with a number.
3.  No spaces around the = sign while assigning a value.
4.  Use { } when referencing variables within strings to avoid ambiguity.

### How to Use a Variable in echo
### Example:

    fruit="Apple"
    echo "I like ${fruit}s."  # Correct

   
    output:
    I like Apples.

### What is a Constant Variable
A **constant variable** is a variable whose value cannot be changed after it is assigned. In shell scripting, you can make a variable read-only using the `readonly` command.

## Declaring a Constant Variable
Use the `readonly` keyword to make a variable constant.

### Example:

    readonly PI=3.14
    echo "Value of PI: $PI"

# Trying to modify the constant variable
    PI=3.1415  # This will cause an error

    Output:
    Value of PI: 3.14
    script.sh: line X: PI: readonly variable

### System Variables
## **Common System Variables**
| Variable  | Description |
|-----------|-------------|
| `$HOME`   | User's home directory |
| `$USER`   | Current logged-in username |
| `$SHELL`  | Default shell (e.g., `/bin/bash`, `/bin/zsh`) |
| `$PATH`   | Directories to search for executable files |
| `$PWD`    | Current working directory |
| `$OLDPWD` | Previous working directory |
| `$EDITOR` | Default text editor (e.g., `nano`, `vim`) |
| `$LANG`   | System language settings |
| `$LOGNAME` | Current logged-in username |
| `$TERM`   | Terminal type (e.g., `xterm`, `vt100`) |
| `$HISTFILE` | Path to history file |
| `$HISTSIZE` | Number of history commands stored in memory |

---

## **Shell-Specific Variables**
| Variable        | Description |
|----------------|-------------|
| `$BASH_VERSION` | Bash shell version |
| `$BASH_SOURCE`  | Name of the script being executed |
| `$BASHPID`      | Process ID of the current Bash shell |
| `$PS1`          | Primary shell prompt format |

---

## **Process & System Variables**
| Variable | Description |
|----------|-------------|
| `$$`    | Process ID of the current shell |
| `$!`    | Process ID of the last background process |
| `$?`    | Exit status of the last executed command |
| `$#`    | Number of arguments passed to a script |
| `$*`    | All arguments passed to a script as a single string |
| `$@`    | All arguments passed to a script as separate strings |

---

## **Networking Variables**
| Variable     | Description |
|-------------|-------------|
| `$HOSTNAME` | System's hostname |
| `$DISPLAY`  | Display server used in GUI systems |
| `$SSH_CLIENT` | IP address of the SSH client |
| `$SSH_TTY`  | TTY device used for SSH sessions |

### Variable Scope
#### Local Variable


A local variable is only accessible within the current shell session.

    local_var="Local"
    echo $local_var  
    
    Output: Local


#### Global Variable
A global variable is accessible in all shells and child processes.
These variables are available to all processes and shell sessions.
They are defined using export, making them available to child processes.

    export global_var="Global"
    echo $global_var  
    
    Output: Global

#### Special Variables

Special variables are predefined by the shell and provide useful information about the shell environment, script execution, and process management.

### List of Special Variables

| Variable | Description |
|----------|-------------|
| `$0`     | Name of the script |
| `$1, $2, ...` | Command-line arguments passed to the script (e.g., `$1` is the first argument) |
| `$#`     | Number of arguments passed to the script |
| `$*`     | All command-line arguments as a single string |
| `$@`     | All command-line arguments as separate strings |
| `$$`     | Process ID (PID) of the current shell |
| `$!`     | Process ID (PID) of the last background process |
| `$?`     | Exit status of the last executed command |

---

## Explain Arrays
### What is an Array in Shell Scripting?
An **array** in shell scripting is a collection of multiple values stored under a single variable name. Arrays help in managing multiple data elements efficiently.

## Features of Arrays:
- Can store multiple values in a single variable.
- Indexed numerically, starting from `0`.
- Can be accessed using index numbers.

#### **Declaring an Array**

    my_array=("Apple" "Banana" "Cherry" "Mango")


### Accessing Elements in an Array
Use the **index number** to retrieve specific values from an array.  
Array indexing in shell scripting starts from **0**.

## Example:

    fruits=("Apple" "Banana" "Cherry" "Mango")

    echo ${fruits[0]}  # Access first element
    echo ${fruits[2]}  # Access third element

    Output:
    Apple
    Cherry


### Printing All Elements in an Array
To print all elements of an array, use `@` or `*` inside curly braces `{}`.

## Example:

    fruits=("Apple" "Banana" "Cherry" "Mango")

    echo ${fruits[@]}  # Prints all elements

    or 

    echo ${fruits[*]}

    Output:
    Apple Banana Cherry Mango

### Getting the Length of an Array
To get the number of elements in an array, use `#` before the array name.

## Example:

    fruits=("Apple" "Banana" "Cherry" "Mango")

    echo ${#fruits[@]}  # Prints the number of elements in the array

    or 

    echo ${#fruits[*]} 

    Output:
    4

### Defining and Accessing an Empty Array
If you want to define an empty array in shell scripting, you can do it like this:

## Example:

    emptyArray=()

If you try to access an element from an **empty array**, it will return an empty result because no values have been assigned yet.

## Example:

    emptyArray=()

# Accessing the first element of an empty array
    echo ${emptyArray[0]}  # This will not display anything

    Output:
    (Empty output)   

### Adding Values and Accessing to the Empty Array
After defining an empty array, you can add values to it, and then accessing those values will work as expected.

## Example:

    emptyArray+=("Apple")   # Add "Apple" to the array
    emptyArray+=("Banana")  # Add "Banana" to the array

# Accessing the first element
    echo ${emptyArray[0]}   # Prints "Apple"

    Output:
    Apple
   
# Accessing the second element
    echo ${emptyArray[1]}   # Prints "Banana"

    Output:
    Banana

# Alternative: Adding Multiple Values

You can add multiple values to an array at once by listing them within the parentheses.

## Example:

    emptyArray+=("Cherry" "Mango" "Orange")

# Printing all elements
    echo ${emptyArray[*]}   # Prints "Apple Banana Cherry Mango Orange"

    Output:
    Apple Banana Cherry Mango Orange

# How to Get Specific Values from an Array

To get specific values from an array, you can access the array using the **index** of the element you want to retrieve. In shell scripting, arrays are zero-indexed, meaning the first element has an index of **0**.


### How to Get Specific Values from an Array
<!-- Content goes here -->

### How to Update an Array
<!-- Content goes here -->

### What is a Key-Value Pair in an Array?
<!-- Content goes here -->

### Defining an Associative Array
<!-- Content goes here -->

---

## Explain Strings
### What is a String in Shell Scripting?
<!-- Content goes here -->

### Types of Strings in Shell
<!-- Content goes here -->

### String Operations
<!-- Content goes here -->

---

## User Interaction
### How to Take a User Input (Basic User Input)
<!-- Content goes here -->

### Taking Input on the Same Line
<!-- Content goes here -->

### Hiding User Input (Password)
<!-- Content goes here -->

### Taking Multiple Inputs in One Line
<!-- Content goes here -->

---

## Operations in Shell
### Arithmetic Operations
<!-- Content goes here -->

### Comparison Operations
<!-- Content goes here -->

### String Operations
<!-- Content goes here -->

### Logical Operations
<!-- Content goes here -->

---

## Control Statements
### if Statement
<!-- Content goes here -->

### if-else Statement
<!-- Content goes here -->

### elif Statement
<!-- Content goes here -->

### case Statement
<!-- Content goes here -->

### Jump Statement
<!-- Content goes here -->

### Select Statement
<!-- Content goes here -->

---

## Loops (Iteration)
### For Loop
<!-- Content goes here -->

### While Loop
<!-- Content goes here -->

### Until Loop
<!-- Content goes here -->

### Infinite Loop
<!-- Content goes here -->

---

## What is Function
### How to Make a Function
<!-- Content goes here -->

### Function with Parameters
<!-- Content goes here -->

### Function with Return Value
<!-- Content goes here -->

### Shifting Arguments
<!-- Content goes here -->

---

## Other Useful Concepts
### Redirection, Bash Variables, Sleep, Exit, Logger, Dev/Null
<!-- Content goes here -->

### Debugging Methods
<!-- Content goes here -->

### Run Scripts in the Background
<!-- Content goes here -->

### Crontab Usage
<!-- Content goes here -->

---

## Projects in Shell Scripting
### Monitoring Free RAM Space
<!-- Content goes here -->

### Monitoring Free DISK Space and Sending an Alert Email
<!-- Content goes here -->

### Create a User and Display Information
<!-- Content goes here -->

---

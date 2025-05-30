# 🚀 Bash Scripting Full Roadmap (From noob to 1337 )

## 1. **Basics of Shell & Bash**

* 1.1 What is a shell? What is Bash?
* 1.2 Terminal vs Shell vs Bash
* 1.3 How to run a Bash script
* 1.4 Shebang (`#!/bin/bash`)
* 1.5 Making scripts executable (`chmod +x`)
* 1.6 Running scripts with `./script.sh` or `bash script.sh`

## 2. **Variables**

* 2.1 Declaring variables (`name="John"`)
* 2.2 Accessing variables (`$name`)
* 2.3 Quoting (`"$var"` vs `$var`)
* 2.4 Environment vs local variables
* 2.5 `readonly` and `unset`

## 3. **User Input and Arguments**

* 3.1 `read` command for user input
* 3.2 Positional arguments (`$1`, `$2`, ...)
* 3.3 Special variables (`$@`, `$#`, `$?`, `$0`, etc.)
* 3.4 Shift operator (`shift`)

## 4. **Operators**

* 4.1 Arithmetic operators (`+`, `-`, `*`, `/`)
* 4.2 Relational operators (`-eq`, `-ne`, `-lt`, `-gt`, etc.)
* 4.3 Boolean operators (`&&`, `||`, `!`)
* 4.4 String comparison operators (`=`, `!=`, `>`, `<`)
* 4.5 File test operators (`-e`, `-f`, `-d`, etc.)

## 5. **Conditional Statements**

* 5.1 `if`, `else`, `elif`
* 5.2 Using `[ ]`, `[[ ]]`, and `(( ))`
* 5.3 Nested conditionals
* 5.4 Case statements (`case ... esac`)

## 6. **Loops**

* 6.1 `for` loops (range, list, C-style)
* 6.2 `while` loops
* 6.3 `until` loops
* 6.4 Loop control: `break`, `continue`
* 6.5 Reading files line by line in a loop

## 7. **Functions**

* 7.1 Defining and calling functions
* 7.2 Function arguments
* 7.3 `return` and `exit`
* 7.4 `local` vs global variables in functions
* 7.5 Using functions for code reuse and clarity

## 8. **Arrays**

* 8.1 Declaring and accessing arrays
* 8.2 Looping through arrays
* 8.3 Associative arrays (key-value)
* 8.4 Array operations (length, push/pop, etc.)

## 9. **Input/Output (I/O)**

* 9.1 `echo` and `printf`
* 9.2 Reading input with `read`
* 9.3 Redirecting output/input (`>`, `>>`, `<`)
* 9.4 Piping (`|`)
* 9.5 File descriptors and advanced redirection (`2>`, `&>`, `<<<`)

## 10. **Error Handling**

* 10.1 Checking exit status (`$?`)
* 10.2 `set -e`, `set -u`, `set -o pipefail`
* 10.3 Using traps (`trap` command)
* 10.4 Defensive scripting techniques

## 11. **File and String Manipulation**

* 11.1 Reading from and writing to files
* 11.2 String manipulation (length, substring, replace)
* 11.3 Pattern matching (wildcards, globbing)
* 11.4 Grep, cut, awk, sed basics (used with scripts)

## 12. **Script Debugging**

* 12.1 `bash -x script.sh`
* 12.2 `set -x` / `set +x` inside scripts
* 12.3 Adding logs with timestamps

## 13. **Advanced Scripting**

* 13.1 Argument parsing with `getopts`
* 13.2 Signal handling with `trap`
* 13.3 Background jobs & processes (`&`, `wait`, `kill`)
* 13.4 Using `cron` for automation
* 13.5 Colorizing output
* 13.6 Working with date and time

## 14. **Shell Script Projects (Practice)**

* 14.1 Backup script with logs
* 14.2 Disk usage report
* 14.3 Simple password generator
* 14.4 User account checker
* 14.5 Log file analyzer
* 14.6 Menu-based interactive tool

## 15. **Best Practices**

* 15.1 Consistent indentation and formatting
* 15.2 Adding comments and documentation
* 15.3 Avoiding global variables
* 15.4 Using `#!/bin/bash -euo pipefail`
* 15.5 Structuring large scripts with functions and error checks

## 16. **Linux Command Integration**

Learn to use Bash with:

* `grep`, `awk`, `sed`, `cut`, `sort`, `uniq`
* `find`, `xargs`, `tee`, `head`, `tail`
* `tar`, `zip`, `scp`, `rsync`
* System commands like `top`, `ps`, `df`, `du`

## 17. **Shell Scripting Interview & Real-World Prep**

* 17.1 Solve 100+ real-world scripting questions
* 17.2 Practice automation tasks
* 17.3 Bash scripting interview Q\&A
* 17.4 Create a GitHub repo with your Bash projects

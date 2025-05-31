## Variables

- Double quotes: `$var` is expanded
- Single quotes: `$var` is treated as plain text
```shell

echo "Hello, $name"   # Hello, Alice
echo 'Hello, $name'   # Hello, $name

```

###  Environment vs Local Variables

- Local: Only for current shell/script
- Environment: Available to child processes

```shell

export age=25    # Environment variable

```

#### read-only and unset

```shell
readonly pi=3.14
pi=3.1415 # can change it is like constant

name="alice"
unset name
echo $name #output: empty
```

## Special Variables

| Variable      | Meaning                        |
| ------------- | ------------------------------ |
| `$0`          | Script name                    |
| `$1`, `$2`, … | Positional arguments           |
| `$#`          | total Number of arguments      |
| `$@`          | All arguments, indiidual quote |
| `$?`          | Exit status of last command    |
| `$$`          | Current script's PID           |
| $*            | all argument as single string  |

## `read` – Take User Input

You can take single or multiple input
use -s for silent input like pass
use -t for timeout


## String Comparison Operators

|Operator|Meaning|
|---|---|
|`==`|equal|
|`!=`|not equal|
|`<`|less (ASCII)|
|`>`|greater|
|`-z`|is empty|
|`-n`|is not empty|

## Boolean Operators

Used for combining conditions.

|Operator|Meaning|
|---|---|
|`!`|NOT|
|`-a`|AND (old)|
|`-o`|OR (old)|
|`&&`|AND (new)|

## File Test Operators

|Operator|Meaning|
|---|---|
|`-e`|File exists|
|`-f`|Regular file|
|`-d`|Directory|
|`-r`|Readable|
|`-w`|Writable|
|`-x`|Executable|

---

## Array

arrays are of two types in bash
- indexed arrays
- associative arrays(string index)

#### declaring a index
```shell

fruits=("apple" " banana" "orange")

```


accessing array:

```shell

echo ${fruits[1]}
```

length of array:

```shell

echo ${#fruits[@]} # number of elements


```

### associative arrays:


```shell

declare -A capitals
capitals[France]="paris"
capitals[Germany]="berlin"
capitals[india]="rome"

#accesing the array
echo ${capitals[india]}

```

|Operation|Syntax Example|
|---|---|
|Declare Indexed|`array=(a b c)`|
|Declare Associative|`declare -A assoc; assoc[key]=val`|
|Access Element|`${array[0]}` or `${assoc[key]}`|
|All Elements|`${array[@]}` or `${assoc[@]}`|
|All Keys|`${!array[@]}` or `${!assoc[@]}`|
|Length|`${#array[@]}`|
|Unset Element|`unset array[1]`|
|Clear Entire Array|`unset array` or `array=()`|

## Input and output

| Symbol | Purpose                     |
| ------ | --------------------------- |
| `>`    | Redirect output (overwrite) |
| `>>`   | Redirect output (append)    |
| `<`    | Redirect input from file    |



## **Piping (`|`)**

Pipes send the **output of one command as input to another**.

**Syntax:**
```shell
command1 | command2
```


### 🔄 **Example:**

bash
`ls | grep "log"`
Here, the output of `ls` is filtered by `grep` to show files containing "log".

## **File Descriptors and Advanced Redirection**

|FD|Meaning|
|---|---|
|0|Standard Input|
|1|Standard Output|
|2|Standard Error|

|Concept|Syntax Example|
|---|---|
|Print text (`echo`)|`echo "Hello"`|
|Formatted output (`printf`)|`printf "Name: %s\n" "Alice"`|
|Read input|`read name`|
|Redirect output (overwrite)|`echo "text" > file.txt`|
|Redirect output (append)|`echo "text" >> file.txt`|
|Redirect input|`command < file.txt`|
|Pipe commands|`ls|
|Error redirection|`cmd 2> error.log`|
|Output + error redirection|`cmd &> out.log` or `cmd > out 2>&1`|
|Here string|`command <<< "input"`|

# Error handling

| Feature           | Purpose                           | Syntax Example                 |
| ----------------- | --------------------------------- | ------------------------------ |
| `$?`              | Check exit status of last command | `if [ $? -ne 0 ]; then ...`    |
| `set -e`          | Exit on any command failure       | `set -e`                       |
| `set -u`          | Treat unset variables as error    | `set -u`                       |
| `set -o pipefail` | Detect pipeline failures          | `set -o pipefail`              |
| `trap`            | Catch signals for cleanup         | `trap 'rm temp' EXIT`          |
| Defensive checks  | Validate input, check files, etc. | `[[ -f "file" ]]`, regex, etc. |
# File and string manupulation

|Tool/Concept|Purpose|Example|
|---|---|---|
|`>` / `>>`|Write/append to file|`echo "Hi" >> file.txt`|
|`read` loop|Read file line by line|`while read line; do ... done < file.txt`|
|`${#str}`|String length|`${#str}`|
|`${str:pos:len}`|Substring|`${str:0:4}`|
|`*`, `?`, `[]`|Pattern matching (globbing)|`*.txt`, `file?.sh`, `[a-z].log`|
|`grep`|Search for patterns|`grep "error" file`|
|`cut`|Extract specific fields/characters|`cut -d':' -f1`|
|`awk`|Advanced text processing|`awk '{print $1}'`|
|`sed`|Search & replace, edit text|`sed 's/old/new/' file`|







## **Pattern Matching (Globbing and Wildcards)**

|Pattern|Description|Example Match|
|---|---|---|
|`*`|Matches any string (zero or more)|`file*` matches `file1`, `file_test`|
|`?`|Matches any single character|`file?.txt` matches `file1.txt`|
|`[abc]`|Matches one character from the set|`f[aeiou]le` matches `file`, `fule`|
|`[a-z]`|Matches range of characters|`file[0-9]` matches `file1`, `file9`|


## Script debugging

|Feature|Purpose|Syntax / Example|
|---|---|---|
|`bash -x`|Trace all commands in a script|`bash -x script.sh`|
|`set -x`|Start command tracing in script|`set -x`|
|`set +x`|Stop tracing|`set +x`|
|Timestamp logs|Track when each step runs|`log() { echo "[\$(date)] \$1"; }`|
|Log to file|Store debug info persistently|`echo "[\$(date)] msg" >> log.txt`|

## Advance topics

| **Section** | **Concept**                     | **Description**                                                | **Key Commands / Syntax**                     | **Examples**                                                                                             |
| ----------- | ------------------------------- | -------------------------------------------------------------- | --------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| 13.1        | Argument Parsing with `getopts` | Used to parse **short options** (`-a`, `-b`) passed to scripts | `getopts ":options"``case $opt in ...`        | `./script.sh -u admin -p 1234``while getopts ":u:p:" opt; do case $opt in u) USER=$OPTARG ;; esac; done` |
| 13.2        | Signal Handling with `trap`     | Handle interruptions like `Ctrl+C` or script exit              | `trap "commands" SIGNAL`                      | `trap "echo Goodbye; exit" SIGINT``trap "cleanup" EXIT`                                                  |
| 13.3        | Background Jobs & Processes     | Run processes in background and manage them                    | `command &``wait $pid``kill $pid`             | `sleep 30 & PID=$!``wait $PID``kill $PID`                                                                |
| 13.4        | Using `cron` for Automation     | Schedule repetitive tasks (daily, hourly, etc.)                | `crontab -e``* * * * * command`               | `0 17 * * * /home/user/backup.sh``crontab -l`                                                            |
| 13.5        | Colorizing Output               | Add colored text to terminal output                            | `echo -e "\e[COLORmTEXT\e[0m"`                | `echo -e "\e[31mError!\e[0m"` (Red)`echo -e "\e[32mSuccess!\e[0m"` (Green)                               |
| 13.6        | Working with Date & Time        | Get and format date/time, generate timestamps, date math       | `date``date +%F``date -d "+2 days"``date +%s` | `date "+%Y-%m-%d %H:%M:%S"``date -d "yesterday"``filename="backup_$(date +%F_%H-%M-%S).tar.gz"`          |





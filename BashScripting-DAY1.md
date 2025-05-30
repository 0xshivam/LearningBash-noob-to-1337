start -->  #!/bin/bash

##### Taking input

```bash
read -p "enter  any text: " variable
```

##### Conditional statements and Positional arguments

Conditionals:
```shell
if [ condition ]; then
  # do something
else
  # do something else
fi

```
 Note: there must be gap in [ ], the condition should be written with spaces on both side of square brackets, use ; after condition, also use fi in the end.

Positional arguments:

INPUT:
```shell

#!/bin/bash

echo "Hello, $1!"
echo "You are $2 years old."

```
Run it with args ex `./hello.sh john 25`
OUTPUT: 
```shell

Hello, John!
You are 25 years old.

```
 note $0 is for script filename

#### LOOPS

**for loop syntax:** Do something a fixed number of times
```shell

for var in item1 item2 item3; do
  # do something with $var
done

```

example 1:

```shell

#!/bin/bash

for name in Alice Bob Charlie; do
  echo "Hello, $name!"
done

```

example 2:
```shell
for count in {1..100}
do 
	echo "$count "
done
```


**While loop** Do something as long as condition is true

syntax:

```shell

while [ condition ]; do
  # do something
done

```
 example:
 ```shell
#!/bin/bash

count=1  # 🟢 Always no space around '='

while [ "$count" -le 5 ]; do
  echo "Count is $count"
  count=$((count + 1))  # increment count
done

```

In **Bash**, a **semicolon (`;`) is like saying "Now move to the next command."**

It **separates two commands** when they are on the **same line**.

example:
```shell
for i in 1 2 3; do
  echo $i
done

```

### Functions

syntax:
```shell

function_name() {
  # some commands
}

        #OR


function function_name {
  # some commands
}
 
function_name #calling the function
```


example:

```shell

#!/bin/bash

say_hello() {
  echo "Hello, friend!"
}

# Call the function
say_hello

```


**Note:**

- `(( ... ))` is used for **math (arithmetic)**.
- `[ ... ]` is used for **conditions**.
- `{ ... }` is used for **code blocks**.
- [ [ ... ] ] why use double? because its for bash and helps prevent stupid error.


| Operator | Description              |
| -------- | ------------------------ |
| `-eq`    | Equal to                 |
| `-ne`    | Not equal to             |
| `-lt`    | Less than                |
| `-le`    | Less than or equal to    |
| `-gt`    | Greater than             |
| `-ge`    | Greater than or equal to |

Note: The quotes `" "` are there to **protect your script from crashing** when the variable is **empty or has spaces**.


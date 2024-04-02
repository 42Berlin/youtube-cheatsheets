# Moving around

|Command|Description|Common options
|-------|-----------|--------------
|`~> pwd`| Print working directory
|`~> cd`| Change directory
|`~> ls`| List content | `-a` list all, `-l` long output
|`~> mkdir new_dir`| Create new directory

# Output
|Command|Description|Common options
|-------|-----------|--------------
|`~> cat file ...`| Concatenate and print
|`~> head file`| Display top 10 lines
|`~> head file`| Display last 10 lines
|`~> wc file`| Count words | `-c` for bytes, `-m` for characters, `-l` for lines
|`~> echo sthg`| Print in the terminal

# Dealing with files
|Command|Description|Common options
|-------|-----------|--------------
|`~> cp src dst`| Copy content
|`~> mv src dst`| Move content
|`~> rm file`| Remove content | `-r` for directories
|`~> wget url`| Download content
|`~> touch file`| Edit timestamp of a file

# Searching
|Command|Description|Common options
|-------|-----------|--------------
|`~> find path -name "sthg"`| Locate sthg in path
|`~> grep pattern src`| Locate lines that contain pattern in src | `-G` to use regex, `-R` to look through all files of a directory recursively

# Permissions and ownership
|Command|Description|Common options
|-------|-----------|--------------
|`~> chmod permissions content`| Change mode of content to permissions
|`~> chown user content`| Change owner of content to user
|`~> sudo cmd`| Gain root privileges to execute cmd


# Redirections and pipes
|Symbol|Description
|-------|-----------
|`> output`| Redirect output
|`>> output`| Redirect output in append mode
|`< input`| Redirect input
|`2> error`| Redirect errors
|`2>> error`| Redirect errors in append mode
|`2>&1`| Merge errors with standard input
|`2> /dev/null`| Discard errors
|`\|`| Use output of left-side as input to right-side
|`;`| Execute right-side after left-side


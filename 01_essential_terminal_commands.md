# Table of Contents

- [Moving around](#moving-around)
  - [pwd](#pwd)
  - [cd](#cd)
  - [ls](#ls)
  - [mkdir](#mkdir)
- [Output](#output)
  - [cat](#cat)
  - [head](#head)
  - [tail](#tail)
  - [wc](#wc)
  - [echo](#echo)
- [Dealing with files](#dealing-with-files)
  - [cp](#cp)
  - [mv](#mv)
  - [rm](#rm)
  - [wget](#wget)
  - [touch](#touch)
- [Searching](#searching)
  - [find](#find)
  - [grep](#grep)
- [Permissions and ownership](#permissions-and-ownership)
  - [chmod](#chmod)
  - [chown](#chown)
  - [sudo](#sudo)
- [Redirections and pipes](#redirections-and-pipes)
  - [Redirections](#redirections)
  - [Pipes and command separators](#pipes-and-command-separators)
    - [Pipes](#pipes)
    - [Command separators](#command-separators)


# Moving around
[Back to TOC](#table-of-contents)
## pwd
**P**rint **wo**rking **di**rectory: displays the current working directory where all commands will be executed
```shell
~> pwd
/Users/theozanchi
```

## cd
**C**hange **d**irectory: can be used with an absolute or relative path.
```shell
~> cd /home/Desktop/some_directory
```

`..` brings you one directory up
```shell
~> cd ..
```

`~` takes you to your home directory
```shell
~> cd ~
```

## ls
**L**i**s**t shows you everything in your current working dircetory
```shell
~> ls
Applications/                               Library/                                   
Desktop/                                    Movies/                                    
Documents/                                  Music/                                     
Downloads/                                  Pictures/                                   
```

`-a` flag includes hidden files in the display
```shell
~> ls -a
./                                          .condarc                                    .npm/                                       .wakatime.cfg
../                                         .config/                                    .p2/                                        .zoomus/
.CFUserTextEncoding                         .cups/                                      .pylint.d/                                  .zsh_history
.DS_Store                                   .docker/                                    .python_history                             .zshrc
.QtWebEngineProcess/                        .eclipse/                                   .python_history-02547.tmp                   Applications/
.Rhistory                                   .gitconfig                                  .python_history-27745.tmp                   Desktop/
```

`-l` flag uses long output for the display 
```shell
~> ls -l
total 8
drwx------	 5 owner  group   160  7 fév 16:52 Applications/
drwx------   5 owner  group   160 28 oct 13:59 Desktop/
drwx------  18 owner  group   576  9 fév 21:56 Documents/
drwx------  69 owner  group  2208 11 fév 20:13 Downloads/
drwx------ 106 owner  group  3392  4 aoû  2023 Library/
drwx------   5 owner  group   160 10 avr  2023 Movies/
drwx------   7 owner  group   224 10 avr  2023 Music/
drwx------   6 owner  group   192 10 avr  2023 Pictures/
drwxr-xr-x   6 owner  group   192 10 avr  2023 Public/
drwxr-xr-x  22 owner  group   704 17 mai  2023 francinette/
drwxr-xr-x   3 owner  group    96 29 aoû  2016 lib/
-rw-r--r--   1 owner  group     6 16 oct 17:11 test.txt
```
The output contains the following information:
* `drwxrwxrwx`: the first letters indicates the type of object (among which `d` for directories, `-` for standard files). The next three `rwx` blocks indicates `r`ead, `w`rite and e`x`ecute permissions for the user, the group and others.
* Number of links to the object
* The owner
* The group
* The size
* The last modification date
8 The name

## mkdir
**M**a**k**e **dir**ectory creates a new directory
```shell
~> mkdir new_directory
```

# Output
[Back to TOC](#table-of-contents)
## cat
Con**cat**enate and print: displays the content of a file in the terminal
```shell
~> cat test.txt
hello world
```

## head
Display the top 10 lines of a file in the terminal
```shell
~> head hhgttg.txt 
The Hitch Hiker's Guide to the Galaxy 
for Jonny Brock and Clare Gorst 
and all other Arlingtoniansfor tea, sympathy, and a sofa
Far out in the uncharted backwaters of the unfashionable  end  of
the  western  spiral  arm  of  the Galaxy lies a small unregarded
yellow sun.
```

## tail
Display the last 10 lines of a file in the terminal
```shell
~> tail hhgttg.txt 
of all possibility.
  
The Vogon turned on the light himself. He picked up the
piece of paper again and placed a little tick in the little box.
Well, that was done. His ship slunk off into the inky void.
In spite of having taken what he regarded as an extremely
positive piece of action, the Grebulon Leader ended up having
a very bad month after all. It was pretty much the same as all
the previous months except that there was now nothing on the
television any more. He put on a little light music instead.
```

## wc
**W**ord **c**ount displays the number of lines, words and bytes of a particular file.
```shell
~> wc hhgttg.txt 
   39776  263723 1534289 hhgttg.txt
```
The information can be accessed independently with flags `-c`/`--bytes` for bytes, `-m`/`--chars` for characters and `-l`/`--lines` for lines
```shell
~> wc -l hhgttg.txt 
   39776 hhgttg.txt
```

## echo
Display text in the terminal
```shell
~> echo hello world 
hello world
```

# Dealing with files
[Back to TOC](#table-of-contents)
## cp
**C**o**p**y files from `source` to `target`
```shell
~> cp temp.txt new.txt
```

`.` and `..` can be used for relative paths
```shell
~> cp ../some_file.txt .
```
```shell
~> cp some_other_file.txt ..
```

## mv
**M**o**v**e files, with absolute or relative paths
```shell
~> mv temp.txt ../another_directory
```

## rm
**R**e**m**ove files or directories.
```shell
~> rm some_file.txt
```

`-r` is required to remove a directory
```shell
~> rm some_directory
rm: cannot remove 'some_directory': Is a directory
```
```shell
~> rm some_directory -r
```

## wget
Download from a URL with the wget method: 
```shell
~> wget https://some_content.tar.xz
```

## touch
Change timestamps with **touch**. If the file does not exist, it is created
```shell
~> touch temp.txt
```
```shell
~> touch -t 0001010000 temp.txt
```
The timestamp is in format `YYMMDDhhmm` and output can be observed with `ls`
```shell
~> ls -l
-rw-r--r-- 1 tzanchi 2023_berlin 0 Jan  1  2000 temp.txt
```

# Searching
[Back to TOC](#table-of-contents)
## find
Find allows you to look for files within a specified directory and below. It supports wildcards as arguments. See our wildcard cheat_sheet for more information (TBC)
```shell
~> > find . -name "*.png"
./test/libft/.media/compilation_complete_screenshot.png
./test/libft/.media/libft_logo.png
./net_practice/img/internet.png
./net_practice/img/host.png
./net_practice/img/switch.png
./net_practice/img/router.png

```

## grep
Grep looks for patterns in files. It returns all lines of the file that contain the pattern
```shell
~> grep hello hhgttg.txt 
could have come and said a big hello to planet Earth, he thought,
the swamps of Squornshellous Zeta are very thoroughly killed  and
underwear, the piles of Squornshellous  mattresses  and  the  man
voice, "and we'll be saying a big hello to all  intelligent  life
"Why hello there!" they said (ticker tape, ticker tape).  "All  I
"Well," he said, "hello my Captain of Vogons Prostetnic, and  how
"I am not a ... hello, can you hear me?"
"Goodbye artificial Universe," he said, "hello real one!"
"Er ..." he said, "hello. Er, look, I'm sorry  I'm  a  bit  late.
"Ah, hello, Number  Two,"  said  the  Captain,  waving  a  cheery
"Er ... hello," they said.
"Oh, hello there," he said to them, "Excuse me  not  getting  up,
"Excuse  me,"  he  said,  "hello.  My  friend  and  I  were  just
"Hello Agda, hello Mella," said Ford.
Dent?  Ah,  hello,  yes. This is Arthur Dent speaking. Don't hang
just  the  end  of  the  game.  We  ought  to get out. Oh, hello,
The moment passed as it regularly  did  on  Squornshellous  Zeta,
Very often on Squornshellous Zeta, whole days would  go  on  like
which live quiet private lives in the marshes  of  Squornshellous
meaning  of  the  word  "vollue",  buy  a  copy of Squornshellous
being  delivered  on  Squornshellous  Zeta,  and certainly not by
revitalize  the  economy of the Squornshellous System. They spent
the entire economy of the Squornshellous System building it. They
"Er, hello?" he said.
creature  from  the  swamps of Squornshellous Zeta had recognized
After an initial flurry of opening hellos, he and Russell  -  the
"Oh, hello, Arthur Dent here. Look, sorry I haven't been  in  for
"Oh hello, is that the Old Elms Hospital? Yes, I was just phoning
the Universe, on Squornshellous Beta to be exact, two  worlds  in
into the life of a simple cushion from Squornshellous Beta.
that really get me down. Oh hello, you again."
he recognised in the distance, and hurried along to say hello,
`Princess Hooli? If I had to stand around saying hello to
villagers he passed said hello, but there was a sense of nervousness
standing there. I go up to say hello, then suddenly I see that
```
Flag `-G` allows to use basic regex in patterns: 
```shell
~> grep -G "hel*" hhgttg.txt
```
Flag `-R` allows you to look for all files recursively of a directory 
```shell
~> grep -R pattern
```

# Permissions and ownership
[Back to TOC](#table-of-contents)
## chmod
Change permissions of some content with **ch**ange **mod**es. `000` removes all permissions while `777` adds all of them 
```shell
~> chmod 000 hhgttg.txt
```

```shell
~> chmod 777 hhgttg.txt
```

## chown
**Ch**ange **own**ership of content
```shell
~> chown another_user hhgttg.txt
```

## sudo
Some commands need root privilege to be executed. Sudo (**S**witch **U**ser **Do**) allows you to gain root privileges for the command that follows
```shell
~> sudo adduser new_user
password:
```

# Redirections and pipes
[Back to TOC](#table-of-contents)
## Redirections
The comparison symbols allow you to redirect the input and output of your commands
```shell
~> cat /etc/os-release  > output
```
Redirect the output of `cat` to a file named `output`

```shell
~> cat /etc/os-release >> output
```
Redirect the output of `cat` to a file named `output` in append mode

```shell
~> grep hello < input
```
Use the file named `input` as an input for `grep`

```shell
~> ls /path/to/non/existing/directory 2> error
```
Redirect the error generated by `ls` to a file named `error`

```shell
~> ls /path/to/non/existing/directory 2>> error
```
Redirect the error generated by `ls` to a file named `error` in append mode

```shell
~> ls /path/to/non/existing/directory 2>&1
```
Merge the error generated by `ls` with `stdin`

```shell
~> ls /path/to/non/existing/directory 2> /dev/null
```
Discard the error generated by `ls` . `/dev/null` is a special file that discard all the data written to it

## Pipes and commands separators
### Pipes
Pipes `|` allow you to use the input of a command as an input to the next command
```shell
~> cat /etc/os-release | grep ubuntu | wc -l
5
```
Here, the content of `/etc/os-release` will be used as an input to `grep`. `grep` will extract the lines that contain `ubuntu` and give it as an input to `wc` that will count the number of lines. The final output is `5`

### Command separators
Semi-colons `;` are used as command separator. Each command after a semi-colon will be executed after the one before and treated as independant
```shell
~> mkdir new_directory ; cd new_directory ; touch new_file.txt
```
In this example, we will:
* Create a new directory `new_directory`
* Move to it
* Create a new file `new_file.txt` inside of it

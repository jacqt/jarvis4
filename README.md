Acknowledgements
----------------
- @jsks and Mr Green from ArchLinux for helping improve this code a lot!

Meta Information
-------------------
Author: Alex Guo.

Contact: chessnut@outlook.com.

Program: JARVIS.

Description: Significantly ease the creating and deleting of aliases.

JARVIS 4.0
----------

Simply "jarvis add" to create a bookmark for the current working directory, or "jarvis add \<alias\>" to create an alias for a command.


Installation
-------------
Download the whole git repo (git clone https://github.com/mallochine/jarvis2).
Run the command that corresponds to your shell:

- make bash 
- make zsh 

```bash
]$ git clone https://github.com/mallochine/jarvis4
Cloning into 'jarvis4'...
remote: Counting objects: 5, done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 5 (delta 0), reused 5 (delta 0)
Unpacking objects: 100% (5/5), done.
$ cd jarvis4
$ make bash
mkdir ~/.jarvis_config
cp jarvis ~/.jarvis_config/jarvis
echo . ~/.jarvis_config/jarvis >> ~/.bashrc;
echo "Restart your shell"
Restart your shell
```

Commands
----------
### jarvis add, jarvis +

Adds the current working directory as a bookmark.

```bash
aguo@unix5:~/Documents/10605$ jarvis add
Type an alias for "cd /afs/andrew.cmu.edu/usr9/aguo/Documents/10605 && pwd && ls", or ^C to quit:
ml
"ml" added as an alias.
```

### jarvis add <alias>

Creates an alias for a command.

```bash
aguo@unix5:~$ jarvis add bics
Type a command for "bics", or ^C to quit:
telnet alexbug.com 5000
"bics" added as an alias.
```

### jarvis del, jarvis -, jarvis del \<bookmark\>, jarvis - \<bookmark\>

(Thanks to Mr Green for conceiving the idea and writing code for this!).

Delete a bookmark.

```bash
$ jarvis -
Type an alias you wish to delete, or ^C to quit:
fics
"fics" deleted.
```

```bash
$ jarvis - fics
"fics" deleted.
```

### jarvis find

Greps the bookmarks for a given query. If a query is given, then jarvis
greps "\<query\>". Otherwise, jarvis will grep using $PWD.

```bash
$ jarvis find bics
alias bics="telnet alexbug.com 4000" # Generated by JARVIS
```

### jarvis edit, jarvis vim

Edits your bookmarks using your shell's default editor (kudos to Mr Green for
writing this!).

```bash
$ jarvis edit
```

```bash
  1 alias j="jarvis" # Generated by JARVIS
  2 alias bics="telnet alexbug.com 4000" # Generated by JARVIS
~
~
~
~
~
~
~
~
~
~
~
~
```

### jarvis all

Lists all the bookmarks you have.

```bash
$ jarvis all
alias j="jarvis" # Generated by JARVIS
alias bics="telnet alexbug.com 4000" # Generated by JARVIS
```

### jarvis help

Displays help info.

```bash
Usage: jarvis [CMD] <file or dir> <bookmark>

Commands
  add | +   Add a bookmark
  del | -   Delete a bookmark
  all       List all bookmarks
  help      Print this help message
```

We would like help with...
---------------------------
- Updating our wiki: https://github.com/mallochine/jarvis2/wiki/jrc---Documentation
- Getting JARVIS4 into the packagement systems of various Linux distributions,
such as apt-get (ubuntu), pacman (archlinux), and more!
- Any helpful suggestions!

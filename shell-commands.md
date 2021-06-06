# Notes about Shell Commands

In Linux or Unix, MacOS or WSL(Windows-Subsystem-for-Linux), terminal commands could be "fun" to use.

As an inexperienced developer, I would like to adapt more and panic less,

for example when login to a container console realizing I was trapped in Vim but only wish to edit a text file X( 

I try to keep notes short and sweet.


(some usage might depend on OS)
## Basics

Two files, concatenation with cat (and '>')
```bash
touch sample1
touch sample2
echo "123" > sample1
echo "abc" > sample2
cat sample1 sample2 > sample1_2
cat sample1_2 sample2 > sample1_2_2
cat sample1 sample2 sample1 > sample1_2_1
```

diff arg: -y compare side-by-side
```bash
diff sample1_2_1 sample2_2_1 -y
```

Print OS info

uname arg: a for all
```bash
man uname
uname -a
```

ps cmd list processes

arg: -A (capital)all users, -v verbose, -m sort by memory usage
```zsh
ps -Avm
```

## Parsing

### grep

print matching lines with line number
```zsh
cat sample1_2_1 | grep 5 -n
```

## Novel

If I were an imaginary hacker and picky about not leaving trace...

appending a space to hide cmds outside history
```bash
history | tail
pwd 
history | tail
```

touch cmd changes modification time
```bash
ls -l
touch sample1_2_1
ls -l
```

shred cmd overwrites specified file(s) for harder discovery

arg: x for exactly same size
```bash
ls -l
shred sample1_2_2 -v -x
cat sample1_2_2
```

## Vim

### Navigation

Smart design of navigational control :P

(Use ESC to quit insert mode)

k:up, j:down, H:top, M:middle,

w:start-of-next-word, e:end-of-next-word, b:start-of-previous-word,

59gg:line-59,

fx:next-x, Fx:previous-x, ;:repeat-jump, ,:reverse-repeat-jump

### General commands

:w write

:q quite

## Collected articles

[Medium: Simple commands like pro](https://javascript.plainenglish.io/simple-commands-in-linux-that-will-make-you-feel-like-a-pro-1407ed928e6c)

[Medium: Safer shell scripts](https://levelup.gitconnected.com/9-tips-for-writing-safer-shell-scripts-b0c185da9bae)
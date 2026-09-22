# Part 1 - Exploring your ~/.bashrc

- 1.1 - Find the file
- Q1
  -rw-r -- r -- 1 kahozi kahozi 3526 Sep 7 08:00 .bashrc
  
  ---
- Q2
  
  1. don't put duplicate lines or lines starting with space in the history.
2. See bash(1) for more options
HISTCONTROL=ignoreboth
**I think it stops duplicate commands from being saved in the history.**
   
---
- Q3
  1. alias ls='ls --color=auto'
2. alias ll='ls -l'
**I think ls is already active, but ll is not active because it has # in front of it.**
   **
---


# Part 2 - Backup before editing
- 2.1 - Make a backup

  
  ---
- Q4

  
-rw-r -- r -- 1 kahozi kahozi 3526 Sep 22 18:45 /home/kahozi/bashrc.backup

  ---
  - 2.2 - Know your escape route
    If anything goes wrong later, you can restore the original with:

cp ~/.bashrc.backup ~/.bashrc
source ~/.bashrc (FOR ME)


---
# Part 3 - Adding a welcome banner
- 3.1 - Edit the file

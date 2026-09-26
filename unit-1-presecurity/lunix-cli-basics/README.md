# Part 1 Getting your bearings

- Q1: What username are you logged in as?


  A:**KAHOZI**
 --- 
- Q2: Are you a member of the sudo group? How can you tell from the output of id?

  A: uid=1000(kahozi) gid=1000(kahozi) groups=1000(kahozi),27(sudo),100(users),986(vboxsf)
  
    - because it say in the out put  27(sudo)
  ---
- Q3: What kernel version is your system running?

  A:Linux kahozi 6.12.107+deb13
  - debian version 13
---
- Q4: What is the difference in the depth of information they give you?

   A:
  
  - whatis whoami gives a short answer about what whoami does.

  - man whoami gives more information and explains the command in more detail.
  ---
- Q5: While in man, how do you (a) search for the word "user" and (b) quit?

   A:
  - /user to search user
  - i press Q to quit
  ---

  # Part 2 Navigation
  ---
  - Q6: What did cd - do?

  A: cd changes directories from on to an other
  ---
  - Q7: What additional information does -l give you over plain ls?
  
   A:It shows things like:

  Permissions

  Owner

  Group

  File size

  Date and time

  File name
  ---
  - Q8: What does -a show that wasn't visible before? Name two examples from the output.

    A: The -a option shows hidden files and folders that were not shown before.
  ---
  Q9: What is the largest file in /var/log? What size is it?

  A: the largestfile is dpkg.log with 802k as the size size
  ---
  Q10: What was modified most recently?

  A: wpmp.db which wwas edited on sep 9. 14🕞
  ---
  # Part 3 Creating and managing files
  ---
  - Q11: Show the command (or commands) you used.

1.Create a directory structure:
 A: mkdir -p ~/cyber-course/unit1 ~/cyber-course/unit2 ~/cyber-course/unit3/osint ~/cyber-course/unit3/recon ~/cyber-course/unit3/crypto ~/cyber-course/scratch
     
  2.Inside ~/cyber-course/scratch/, create three empty files: a.txt, b.txt, c.txt. Verify with ls.
  - touch ~/cyber-course/scratch/a.txt ~/cyber-course/scratch/b.txt ~/cyber-course/scratch/c.txt
ls -l ~/cyber-course/scratch/

3. Copy a.txt to ~/cyber-course/unit1/ with the new name intro.txt. Verify it exists in the new location.
   
 - cp ~/cyber-course/scratch/a.txt ~/cyber-course/unit1/intro.txt
ls -l ~/cyber-course/unit1/

4. Move b.txt to ~/cyber-course/unit2/.
- mv ~/cyber-course/scratch/b.txt ~/cyber-course/unit2/
  
5. Rename c.txt to notes.txt (still in scratch/).
  - mv ~/cyber-course/scratch/c.txt ~/cyber-course/scratch/notes.txt
  ---
 - Q12  What key combination did you use to save? What key combination did you use to exit?


   I used Ctrl+O to save the file, then pressed Enter to confirm the filename. I used Ctrl+X to exit nano.
   

 7.  Run cat ~/cyber-course/unit1/intro.txt to confirm the contents.

 8. Try to delete ~/cyber-course/scratch/ with rmdir. What happens?
    
 --- 
 
  - Q13 Why did rmdir fail (or succeed)?
    
    rmdir failed because the scratch/ directory was not empty. The rmdir command only removes empty directories.

## Part 4 Viewing Files

### Q14: Which Debian version do you have?

**Answer:**  
I have Debian [PRETTY NAME="Debian GNU/Linux 13 (trixie)"].

### Q15: What kind of messages do you see? Are they recent?

**Answer:**  
The messages are mainly system and service activity, such as processes starting or stopping, system events, and other system-related information. Yes, the messages are recent because `/var/log/syslog` contains recent system activity.

## Part 5 Searching

### Q16: How many lines were returned?

**Answer:**  
I used:

grep "ssh" /etc/services | wc -l

The number of lines returned was: 1 line 

### Q17: How would you modify the command to show only `.conf` files modified in the last 7 days?

**Answer:**  
I would use:

find /etc -name "*.conf" -mtime -7

### Q18: Where are these commands actually located on the filesystem?

**Answer:**  
I used:

which ls
which nano

The commands are usually located at:

ls: /usr/bin/ls
nano: /usr/bin/nano

## Part 6 History, redirection, and pipes

### Q19: What does the `|` symbol do here?

**Answer:**  
I used:

history | tail -n 20

The `|` sends the output from `history` to `tail`. It shows the last 20 commands.

## Part 7 Archives

### Q22: Confirm with `ls -la` that the extraction worked. What did you find inside?

**Answer:**  
I used:

ls -la

I found the `unit1` folder inside the `test-extract` directory. The extraction worked.

### Q23: What do the flags `c`, `z`, `v`, and `f` each mean?

**Answer:**  
- `c` = create a new archive
- `z` = use gzip compression
- `v` = show the files being processed
- `f` = use the filename given

### Q20: What is the difference between `>` and `>>`?

**Answer:**  
`>` replaces the old content in the file.

`>>` adds new content to the end of the file.

### Q21: What was the output, and why?

**Answer:**  
I got:

hello cyber world

It showed this because the word `cyber` was found in the sentence.

### Question: What is the difference between `clear` and `Ctrl+L`?

**Answer:**  
Both clear the terminal screen. `clear` is a command, while `Ctrl+L` is a keyboard shortcut. 

## Part 7 Archives

### Q22: Confirm with `ls -la` that the extraction worked. What did you find inside?

**Answer:**  
I used:

ls -la

I found the `unit1` folder inside the `test-extract` directory. The extraction worked.

### Q23: What do the flags `c`, `z`, `v`, and `f` each mean?

**Answer:**  
- `c` = create a new archive
- `z` = use gzip compression
- `v` = show the files being processed
- `f` = use the filename given

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

    A: mkdir -p ~/cyber-course/unit1 ~/cyber-course/unit2 ~/cyber-course/unit3/osint ~/cyber-course/unit3/recon ~/cyber-course/unit3/crypto ~/cyber-course/scratch
  ---

# Part I
### 1. make a directory called first
### ans: find screenshots here: [before](/terminale-and-unix/terminal-basics-screenshots/terminal-basics-solution1-before.png) and [after](/terminal-and-unix/terminal-basics-screenshots/terminal-basics-solution1-after.png)

### 2. change directory to the first folder
### ans: find screenshots here: [before](/terminal-and-unix/terminal-basics-screenshots/terminal-basics-solution2-before.png) and [after](/terminal-and-unix/terminal-basics-screenshots/terminal-basics-solution2-after.png)

### 3. create a file called person.txt
### ans: find screenshots here: [before](/terminal-and-unix/terminal-basics-screenshots/terminal-basics-solution3-before.png) and [after](/terminal-and-unix/terminal-basics-screenshots/terminal-basics-solution3-after.png)

### 4. change the name of person.txt to another.txt
### ans: find screenshots here: [before](/terminal-and-unix/terminal-basics-screenshots/terminal-basics-solution4-before.png) and [after](/terminal-and-unix/terminal-basics-screenshots/terminal-basics-solution4-after.png)

### 5. make a copy of the another.txt file and call it copy.txt
### ans: find screenshots here: [before](/terminal-and-unix/terminal-basics-screenshots/terminal-basics-solution5-before.png) and [after](/terminal-and-unix/terminal-basics-screenshots/terminal-basics-solution5-after.png)

### 6. remove the copy.txt file
### ans: find screenshots here: [before](/terminal-and-unix/terminal-basics-screenshots/terminal-basics-solution6-before.png) and [after](/terminal-and-unix/terminal-basics-screenshots/terminal-basics-solution6-after.png)

### 7. make a copy of the first folder and call it second
### ans: find screenshots here: [before](/terminal-and-unix/terminal-basics-screenshots/terminal-basics-solution7-before.png) and [after](/terminal-and-unix/terminal-basics-screenshots/terminal-basics-solution7-after.png)

### 8. delete the second folder
### ans: find screenshots here: [before](/terminal-and-unix/terminal-basics-screenshots/terminal-basics-solution8-before.png) and [after](/terminal-and-unix/terminal-basics-screenshots/terminal-basics-solution8-after.png)

# Part II
### 1. What does the man command do? Type in man rm. How do you scroll and get out?
### ans: The man command displays the system's manual or descriptions for other commands or tools.
### ans: Running a "man rm" resulted to [this](/terminal-and-unix/terminal-and-unix/terminal-basics-screenshots/terminal-basics-solution1-part2.png)
### ans: The 'up' and 'down' as well as 'k' and 'e' keys respectively on the keyboard can be used to scroll.
### ans: The 'q' key can be pressed to get out of the manual.

### 2. Look at the man page for ls. What does the -l flag do? What does the -a flag do?
### ans: The -l flag displays the files and folders in a long format like [this](/terminal-and-unix/terminal-and-unix/terminal-basics-screenshots/terminal-basics-solution2-part2.png) showing the permissions, and groups attached to a file or directory
### ans: The -a flag displays the files and folders without ignoring those starting with . (i.e hidden files) like [this](/terminal-and-unix/terminal-and-unix/terminal-basics-screenshots/terminal-basics-solution2-part2.png)

### 3. Type the following command to download and save the contents of google.com: curl https://www.google.com > google.html
### ans: Command was executed successfully [here](/terminal-and-unix/terminal-and-unix/terminal-basics-screenshots/terminal-basics-solution3-part2.png)

### 4. Use less to look at the contents of google.html.
### ans: Command was executed successfully [here](/terminal-and-unix/terminal-and-unix/terminal-basics-screenshots/terminal-basics-solution4-part2.png)

### 5.Look at the man page for less. Read the section on /pattern. Search for the text hplogo in the google.html file.
### ans: The command used in less was /hplogo which produced [this](/terminal-and-unix/terminal-and-unix/terminal-basics-screenshots/terminal-basics-solution5-part2.png) result

### 6. How do you jump between words in the terminal?
### ans: The combination of 'ctrl' key with 'left' or 'right' key enables one to jump between words while simply using the 'right' or 'left' key alone allows one to move between letters.

### 7. How do you get to the end of a line in terminal?
### ans: The combination of 'ctrl' and 'e' performs the task

### 8. How do you move your cursor to the beginning in terminal?
### ans: The combination of 'ctrl' and 'a' performs the task

### 9. How do you delete a word (without pressing backspace multiple times) in terminal?
### ans: The combination of 'ctrl' and 'w' performs the task

### 10. What is the difference between a terminal and shell?
### ans: The terminal is a visual interface in a computing device that accepts some inputs (commands) from a user and then displays some output afterwards while the processing of input in a terminal is executed by the shell or program running in the terminal. The default for linux distribution is bash, others are zsh, python e.t.c.

### 11. What is an absolute path?
### ans: This is a complete list of directories required to locate a file or folder right from the root directory.

### 12. What is an relative path?
### ans: This a listing of directories needed to locate files or folders from the current working directory.

### 13. What is a flag? Give three examples of flags you have used.
### ans: This is an argument or option passed to a command in order for it to be executed in a particular way. Examples: -l, -a, -h e.t.c.

### 14. What do the r and f flags do with the rm command?
### ans: The r flag is used to remove (delete) directories and their constituents recursively while the f flag ensures files are deleted even if user has no permission and also deletion of files that may not exist without any prompt or error.
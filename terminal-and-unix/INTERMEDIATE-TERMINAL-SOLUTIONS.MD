# Part I
### 1. Create an environment variable called FIRST_NAME and set it equal to your first name (this does not need to be permanent)
### ans: find screenshots [here](/terminal-and-unix/INTERMEDIATE-TERMINAL-SCREENSHOTS/intermediate-terminal-solution1-and-2.png)

### 2. Print the FIRST_NAME variable
### ans: find screenshots [here](/terminal-and-unix/INTERMEDIATE-TERMINAL-SCREENSHOTS/intermediate-terminal-solution1-and-2.png)

### 3. Print out the $PATH variable
### ans: find screenshots [here](/terminal-and-unix/INTERMEDIATE-TERMINAL-SCREENSHOTS/intermediate-terminal-solution3.png)

### 4. What is the $PATH variable?
### ans: This is an environment variable that is used to store executable programs so they can run from anywhere in the terminal

### 5. Why would you want to create an environment variable?
### ans: One of the main reasons for using it is to ensure security of sensitive data.

### 6. How do you permanently save environment variables?
### ans: This is achieved by defining the variable to be exported in a shell configuration file e.g. .bash_profile for a bash shell.

### 7. What is a process?
### ans: This is simply the program running on a computer at an instance.

### 8. How do you list all processes running on your machine?
### ans: By running the 'ps aux' command

### 9. What is a PID?
### ans: This is the process id, it is the number that uniquely identifies the process.

### 10. How do you terminate a process?
### ans: By running the command 'kill PID'. Where PID of the process that needs to be terminated.

### 11. What is the difference between kill and kill -9?
### ans: kill, sends a TERM signal to terminate or end a process appropraitely, while the kill -9, sends a KILL signal to terminate or end a process abruptly. The latter is especially used frozen processes.

### 12. What grep flag allows for case insensitive search?
### ans: -i

### 13. What grep flag allows for a certain number of lines before the match?
### ans: -B

### 14. What grep flag allows for a certain number of lines around the match?
### ans: -C

### 15. What grep flag allows for a certain number of lines after the match?
### ans: A

### 16. Wh-at grep flag allows for full word search?
### ans: -w

### 17 .What grep flag shows you the line number of a match?
### ans: -c
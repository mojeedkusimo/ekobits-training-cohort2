# Part I (Permissions and links)
### 1. Create a file called restricted.txt.
### ans: find screenshots here: [before](/terminal-and-unix/permissions-redirection-and-piping-screenshots/permisions-redirection-and-piping-solution1-before.png) and [after](/terminal-and-unix/permissions-redirection-and-piping-screenshots/permisions-redirection-and-piping-solution1-after.png)

### 2.  Change the permissions on the restricted.txt file to allow the owner to read and write to the restricted.txt file. Do this using the Octal Notation.
### ans: find screenshots [here](/terminal-and-unix/permissions-redirection-and-piping-screenshots/permisions-redirection-and-piping-solution2.png)

### 3. Change the permissions on the restricted.txt file to only allow the owner, group and everyone to read and write and execute the restricted.txt file. Do this using the Symbolic notation.
### ans: find screenshots [here](/terminal-and-unix/permissions-redirection-and-piping-screenshots/permisions-redirection-and-piping-solution3.png)

### 4. Create a folder called secret_files. Inside the secret_files folder create a file called first_secret.txt and another folder called classified. Inside of the classified folder create a file called super_secret.txt.
### ans: find screenshots here: [before](/terminal-and-unix/permissions-redirection-and-piping-screenshots/permisions-redirection-and-piping-solution4-before.png) and [after](/terminal-and-unix/permissions-redirection-and-piping-screenshots/permisions-redirection-and-piping-solution4-after.png)

### 5. Change the permissions on the secret_files to only allow the owner and group to read, write and execute in all the files and folders inside of secret_files. Do this using the Octal Notation.
### ans: find screenshots [here](/terminal-and-unix/permissions-redirection-and-piping-screenshots/permisions-redirection-and-piping-solution5.png)

### 6. Create a hard link for the restricted.txt called hard_link.
### ans: find screenshots [here](/terminal-and-unix/permissions-redirection-and-piping-screenshots/permisions-redirection-and-piping-solution6.png)

### 7. Create a symbolic link for the classified folder called classified_link.
### ans: find screenshots [here](/terminal-and-unix/permissions-redirection-and-piping-screenshots/permisions-redirection-and-piping-solution7.png)

# Part II (Piping and Redirection)
### For the following exercises, create a text file called vegetables.txt with the following text:

### Lettuce
### Amaranth
### Beet
### Celery
### Kale
### Dill
### Cabbage
### Broccoli
### Lettuce
### Amaranth
### Beet
### Spinach
### Chard
### Broccoli
### Cabbage
### Dill

### Write the following terminal commands to do the following

### 1. Sort vegetables.txt.
### ans: find screenshots [here](/terminal-and-unix/permissions-redirection-and-piping-screenshots/permisions-redirection-and-piping-solution1-part2.png)

### 2. Count the number of lines in vegetables.txt.
### ans: The count equals 16 as shown [here](/terminal-and-unix/permissions-redirection-and-piping-screenshots/permisions-redirection-and-piping-solution2-part2.png)

### 3. Create a file called vegetables_sorted.txt which contains all the unique vegetables sorted in ascending order in vegetables.txt (do this without the touch command).
### ans: find screenshots [here](/terminal-and-unix/permissions-redirection-and-piping-screenshots/permisions-redirection-and-piping-solution3-part2.png)

### 4. Create a file called last_three.txt which contains the last three vegetables in the vegetables.txt file (do this without the touch command).
### ans: find screenshots [here](/terminal-and-unix/permissions-redirection-and-piping-screenshots/permisions-redirection-and-piping-solution4-part2.png)

### 5. Count the number of lines the word "Broccoli" appears on (using wc and grep).
### ans: find screenshots [here](/terminal-and-unix/permissions-redirection-and-piping-screenshots/permisions-redirection-and-piping-solution5-part2.png)
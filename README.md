# Project5--Shell-scripting-

# Shell scripting hands on practice

__What is Shell scripting__ : 

Shell scripting is a text file with a list of commands that instruct an operating system to perform certain tasks. Furthermore, shell scripting is a powerful tool commonly used across industries to automate tasks, test solutions, and increase efficiency.

Shell scripting helps in automating repetitive task, for example we can write a script that does the job of cloning 1000 repository and we call it once and the job is done. Besides, we have the advantages of using the script again whenever we are assigned same task.
We can perform shell scripting, in bash,vs code,powershell, and so on. However for this practice we will be using bash from a visual studio code.

Bash script are essentially a series of command and instructions that are executed sequentially in a shell. We can create a shellscript by saving a collection of command in a text file with **.sh** extension.

# **SHELL SCRIPTING SYNTAX ELEMENTS**

# 1. **Variables:**
   
Bash allows you to define and work with variables. Variables can store data of various type such as numbers,strings and array. We can assign values to variables using the **=** operator sign and access their values using the variable name preceding by a **$** sign.

**STEPS:**
- Go to your visual studio bash terminal then create a folder and name it shellscript1 with the command **mkdir shellscript**

  Note: we are using bash from visual studio because it enables us to visually see the file created and also edit on the spot this file while you are also seeing your terminal(command line)

- create a file with the **.sh** extention(for example put in the command:**touch script.sh**) and input the following command in the file  then save
 
#! bin/bash

NAME="Mudiaga"

echo "$NAME"

**Note**: you can write in the file using editor command:**(nano script.sh or vi script.sh or just copy and paste in the file on the vs code)** when done remember to **save** .Furhter this command (**#! bin/bash**) is a command for scripting telling the the system to execute all below the command in the file.

- After saving, set execution command on the command line using: **chmod +x script.sh** and press enter

- To run the script use the command :**bash script.sh**

  Your output should be as image below
  
![image](https://github.com/DevopMudi/Project5--Shell-scripting-/assets/149855241/a9004d06-9cfa-4049-b07b-a7098ce52543)

  
# 2. **Control flow:**
 Bash provide control flow statement like if else for loop, while loop and case statement to control the flow of execution in a script. This statement allow us to make decision, iterate over list and execute different command base on condition.

Example 1: using if else to execute script base on condition:
- Copy the below code and paste on your file then save

 **#! bin/bash**

**#Example script to check if a number is positive, negative or zero**

 

**read -p "Enter a number ?"  Num**

**if [ $Num -gt 0 ]; then**
   
   **echo "The number is Positive."**

**elif [ $Num -lt 0 ]; then**
  
   **echo "The number is Negetive."**

**else**
  
   **echo "The number is Zero."**

**fi**

- Run the command : **bash script.sh**

  Your image and command flow should be as below:

  ![image](https://github.com/DevopMudi/Project5--Shell-scripting-/assets/149855241/36021efa-0dbe-4a79-9e40-dcef37761059)


# 3. **Iterating through a list for a loop:**

   - Copy and paste the below command on the file, then save.

    #! /bin/bash

#Example script to print numbers from 1 to 5 using a for loop

for (( i=1; i<=5; i++ ))

do
 
    echo $i

done


- After saving, run the command: bash script.sh

- Your image should be as below:

  ![image](https://github.com/DevopMudi/Project5--Shell-scripting-/assets/149855241/f42e5a34-97c3-4a68-b664-41a19b22f8dc)


# 4. **Command substitution:**

Command substitution allows you to capture the output of a command use it as a value within your script .

**Note: We can use the backtick or $() syntax for command substitution**

- Example for using the backtip for command substitution: copy and paste the below code on your file, then save  and run the bash script.sh command.

**#! bin/bash**

**#current date**

**read -p "Do you want to know the current date ? " current_date**

**current_date=`date +%Y-%m-%d`**

**echo "$current_date"**

- image should be as below

`![image](https://github.com/DevopMudi/Project5--Shell-scripting-/assets/149855241/5fe2364e-eb81-4cfa-b48d-1ff9a9fccaf4)

  

- Example of Using the syntax for command substitution : copy and paste the below code on your file, then save  and run the bash script.sh command.

 **#! bin/bash**

#current date

**read -p "Do you want to know the current date ? " current_date**

**current_date=$(date +%Y-%m-%d)**


**echo "$current_date"**

Image should be as below:

![image](https://github.com/DevopMudi/Project5--Shell-scripting-/assets/149855241/42d7645c-35d4-4184-8552-915af30dfc33)





# 5.  Input and Out put:

Bash provide various ways to handle input and output.you can use the read command to accept user input and out put text to the console using the echo command as we have done in example image above. Additionally, we we can redirect input and output using the > output to a file,< input to a file, (and pipe the output of one command as input to another)

Further example 1 : Accept user input: 

![image](https://github.com/DevopMudi/Project5--Shell-scripting-/assets/149855241/01b41527-833f-4d6a-9c9f-450b9c6c5564)


further example 2 : Output text to the terminal: **echo "Hello World"**



![image](https://github.com/DevopMudi/Project5--Shell-scripting-/assets/149855241/b015aa48-ea88-4dae-8632-6ee9b5ad8ee9)


Further example 3: Out the result of a command into a file: echo **"hello world" > index.txt**


![image](https://github.com/DevopMudi/Project5--Shell-scripting-/assets/149855241/ddf5c2a9-65c2-462a-94a9-f393bb7f830f)


Further example 4: Passing the content of file as input to a command: **grep "pattern" < input.txt**

![image](https://github.com/DevopMudi/Project5--Shell-scripting-/assets/149855241/80bf2814-fea9-4df2-8449-08539b7bb24a)




# 5.  Functions:
Bash allows you to define and use functions to group related command together. Functions provide away to modularize your code and make it more reuseable. We can define function, using the function key word or simply by declaring the function name followed by parentheses.

Example is to follow as image below

![image](https://github.com/DevopMudi/Project5--Shell-scripting-/assets/149855241/9b57a380-0373-48e4-ace8-e78bf0b6a75b)


# DIRECTORY MANIPULATION AND NAVIGATION

We will write a simple script again as a way to practice more all we have been doing since the begining of our shellscripting.

This below script will display the current directory,create a new directory called "my_directory", change to that directory, create two files inside that directory, list the files,move back one level up, remove the the "my_directory" and its content and finally list the file in the current directory again;

Steps invovle:

- Open a file named navigating-linux-filesystem

- Past the code block below into the file:

  #!/bin/bash

#Display current directory

echo "Current directory: $PWD"

#Create a new directory

echo "Creating a new directory..."

mkdir my_directory

echo "New directory created."

#Change to the new directory

echo "Changing to the new directory..."

cd my_directory

echo "Current directory: $PWD"

#Create some files

echo "Creating files..."

touch file1.txt

touch file2.txt

echo "Files created."

#List the files in the current directory

echo "Files in the current directory:"
ls

#Move one level up

echo "Moving one level up..."

cd ..

echo "Current directory: $PWD"

#Remove the new directory and its contents

echo "Removing the new directory..."

rm -rf my_directory

echo "Directory removed."

#List the files in the current directory again

echo "Files in the current directory:"

ls

- image should display as below:

  ![image](https://github.com/DevopMudi/Project5--Shell-scripting-/assets/149855241/746b468a-a7d9-4b5a-8fea-d39e5234bf87)


![image](https://github.com/DevopMudi/Project5--Shell-scripting-/assets/149855241/32f3b83a-3a4f-467a-8e27-f1a8e262ec36)



# FILE OPERATION AND SORTING 

We will be writing a simple shellscript that focuses on file operation and sorting. 

This script create 3 files(file1.txt, file2.txt, file3.txt), display the file in their current order, sort them alphabeticallly, save the sorted file in sorted_files, remove the original file, rename the sorted file to sorted_files_sorted_alphabeticall.txt and finally display content ofthe final sorted files. 

The following are the steps invovle in doing this.

- Open your terminal and create a file called sorting.sh

- Copy and past the code block below into your file, then save.

  #!/bin/bash

#Create three files

echo "Creating files..."

echo "This is file3." > file3.txt

echo "This is file1." > file1.txt

echo "This is file2." > file2.txt

echo "Files created."

#Display the files in their current order

echo "Files in their current order:"

ls

#Sort the files alphabetically

echo "Sorting files alphabetically..."

ls | sort > sorted_files.txt

echo "Files sorted."

#Display the sorted files

echo "Sorted files:"

cat sorted_files.txt

#Remove the original files

echo "Removing original files..."

rm file1.txt file2.txt file3.txt

echo "Original files removed."

#Rename the sorted file to a more descriptive name

echo "Renaming sorted file..."

mv sorted_files.txt sorted_files_sorted_alphabetically.txt

echo "File renamed."

#Display the final sorted file

echo "Final sorted file:"

cat sorted_files_sorted_alphabetically.txt


- Next step, is to execute permission sorting.sh using this command : **chmod +x sorting.sh**


- Then finally run you script using this command : **bash sorting.sh**

  Your image should be as display below:

![image](https://github.com/DevopMudi/Project5--Shell-scripting-/assets/149855241/a4f952bb-2f12-478f-81d9-235af87030b0)

![image](https://github.com/DevopMudi/Project5--Shell-scripting-/assets/149855241/d1427334-983a-45f6-852f-d38aff56396e)

![image](https://github.com/DevopMudi/Project5--Shell-scripting-/assets/149855241/431e828b-d049-4336-84d9-522c1a569818)


#WORKING WITH NUMBERS AND CALCULATIONS

This script defines two variables,Num1 and Num2 with numeric values, performs basic arithmetic operation (additon,subtraction,division,multiplication,and modulus)
and display the results. It also performs more complex calculation such as raising Num1 to the power of 2 and calculating the square root of Num2 and display those result as well,

Lets proceed.

- On the terminal create a file called **"calculations.sh"** using the command: **touch calcutions.sh**

- Copy and paste the below block below:

  #!/bin/bash

#Define two variables with numeric values

num1=10

num2=5

#Perform basic arithmetic operations

sum=$((num1 + num2))

difference=$((num1 - num2))

product=$((num1 * num2))

quotient=$((num1 / num2))

remainder=$((num1 % num2))

#Display the results

echo "Number 1: $num1"

echo "Number 2: $num2"

echo "Sum: $sum"

echo "Difference: $difference"

echo "Product: $product"

echo "Quotient: $quotient"

echo "Remainder: $remainder"

#Perform some more complex calculations

power_of_2=$((num1 ** 2))

square_root=$(echo "sqrt($num2)" | bc)

#Display the results

echo "Number 1 raised to the power of 2: $power_of_2"

echo "Square root of number 2: $square_root"


- Set execution permission on calculations.sh using this command: **chmod +x calculations.sh**

- Then run the script, using this command: bash calculations.sh


The image should be as below for reference:

![image](https://github.com/DevopMudi/Project5--Shell-scripting-/assets/149855241/8fb2f1f5-498b-4433-b127-4ee1314e472f)

scrow down page below

![image](https://github.com/DevopMudi/Project5--Shell-scripting-/assets/149855241/d203461d-3668-44a8-996d-b0c137609b94)

scrow down page of file below and terminal below

![image](https://github.com/DevopMudi/Project5--Shell-scripting-/assets/149855241/395999ff-51b0-4031-b02a-deb2ff769ca8)

final down page below.


# FILE BACKUP AND TIMESSTAMPING

This aspect is focus on file backup and timestamping. As a Devops engineer,backing up databases and other storage devices is one of the moost common task, you get to carry out.

This script defines the source directory and the backup directory path. It then create a timestamping using the current date and time and create a backup directory with the timestamp append to his name. The script then copy all file from the source directory to the back up directory using cp command with the r option for recursive copying. Finally it display a message indicating the completion of the backup process and shows the path of the backup directory with the timestamp.

Let proceed using the steps below:

- On the terminal, open a file called **"backup.sh"** using the command : **touch backup.sh**

- Copy and paste the block below into the file, then save

  #!/bin/bash

#Define the source directory and backup directory

source_dir="/path/to/source_directory"

backup_dir="/path/to/backup_directory"

#Create a timestamp with the current date and time

timestamp=$(date +"%Y%m%d%H%M%S")

#Create a backup directory with the timestamp

backup_dir_with_timestamp="$backup_dir/backup_$timestamp"

#Create the backup directory

mkdir -p "$backup_dir_with_timestamp"

#Copy all files from the source directory to the backup directory

cp -r "$source_dir"/* "$backup_dir_with_timestamp"

#Display a message indicating the backup process is complete

echo "Backup completed. Files copied to: $backup_dir_with_timestamp"

- Set execution permission on the **backup.sh** using the command: **chmod +x backup.sh**

- Run the script using the command :**bash backup.sh**

  final image should be as below:

  ![image](https://github.com/DevopMudi/Project5--Shell-scripting-/assets/149855241/6fc1b66b-9749-44bb-8e31-d08d322c662d)

- from the above image, it appears like some file are not copy due to directory not being made, I had to adjust/ debug the block but still i will need more training from darey.io for debuging script.

  # For more information contact : Darey.io support team

  


  
























































































































































































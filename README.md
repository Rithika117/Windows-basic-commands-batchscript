# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript

# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
### Step 3:

Execute the necessary commands/batch file for the desired output. 

# WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations
Create a directory named "my-folder"

## COMMAND AND OUTPUT
mkdir "my-folder"
<img width="807" height="484" alt="Screenshot 2026-03-16 200431" src="https://github.com/user-attachments/assets/16758d58-17bb-4cd4-9cd6-7e9690e805a1" />
Remove the directory "my-folder"

## COMMAND AND OUTPUT
rmdir the directory "my-folder"
<img width="533" height="354" alt="Screenshot 2026-03-16 200737" src="https://github.com/user-attachments/assets/2d422633-4248-480e-aa48-c5caeba2890b" />

Create the file Rose.txt

## COMMAND AND OUTPUT
type nul > rose.txt
echo Rose flower is beautiful >> rose.txt

<img width="847" height="120" alt="Screenshot 2026-03-16 201116" src="https://github.com/user-attachments/assets/9ace265c-b59e-4e9b-a49d-be1d6339299f" />

Create the file hello.txt using echo and redirection

## COMMAND AND OUTPUT
echo Hello > hello.txt
type hello.txt

<img width="607" height="228" alt="Screenshot 2026-03-16 201315" src="https://github.com/user-attachments/assets/f6fc0cc3-5e07-4d18-939c-0901f90f34f4" />

Copy the file hello.txt into the file hello1.txt

## COMMAND AND OUTPUT
copy hello .txt hello1.txt
type hello1.txt

<img width="612" height="247" alt="Screenshot 2026-03-16 201549" src="https://github.com/user-attachments/assets/fa8c55a7-e239-4a8a-bde3-310e08bfcef6" />

Remove the file hello1.txt

## COMMAND AND OUTPUT
del hello1.txt

<img width="605" height="381" alt="Screenshot 2026-03-16 201645" src="https://github.com/user-attachments/assets/704dab37-085b-4d17-a4eb-ab53327c1d4d" />

List out the file hello1.txt in the current directory

## COMMAND AND OUTPUT
dir hello1.txt

<img width="528" height="216" alt="Screenshot 2026-03-16 201807" src="https://github.com/user-attachments/assets/95c635b9-d258-4f82-aa5e-9930041a489e" />

List out all the associated file extensions 

## COMMAND AND OUTPUT
assoc

<img width="543" height="416" alt="Screenshot 2026-03-16 201903" src="https://github.com/user-attachments/assets/643cf4cd-8810-48ba-80e8-e74901f30134" />

Compare the file hello.txt and rose.txt

## COMMAND AND OUTPUT
fc hello.txt rose.txt

<img width="582" height="303" alt="Screenshot 2026-03-16 202059" src="https://github.com/user-attachments/assets/81697720-16a2-47b0-973b-ec94092e938c" />


## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".
```
@echo off
set name=Saveetha
echo Hello, %name%!
pause
```

## OUTPUT

<img width="493" height="97" alt="Screenshot 2026-03-16 202211" src="https://github.com/user-attachments/assets/6ff7e284-f074-4eff-a0f7-226b7e7e3b24" />

Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.
```
@echo off
:main
set /p number=Enter a number: 
rem Calculate remainder when divided by 2
set /a remainder=%number% %% 2
if %remainder%==1 (
    echo %number% is an odd number.
) else (
    echo %number% is not an odd number.
)
:choice
set /p continue=Do you want to check another number? (Y/N): 
if /i "%continue%"=="Y" goto main
if /i "%continue%"=="N" goto end
echo Invalid choice, please enter Y or N.
goto choice
:end
echo Thank you for using the odd number checker!
pause
```

## OUTPUT

<img width="784" height="237" alt="Screenshot 2026-03-16 202346" src="https://github.com/user-attachments/assets/1c7240d6-a0fb-411f-949f-be3c578bb4bb" />

Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.
```
@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause


```

## OUTPUT

<img width="767" height="220" alt="Screenshot 2026-03-16 202444" src="https://github.com/user-attachments/assets/ffc8eec9-de7b-493e-ae59-5fbf8a5c3871" />

Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):
```
@echo off
if exist sample.txt (
    echo sample.txt exists.
) else (
    echo sample.txt does not exist.
)
pause
```

## OUTPUT

<img width="468" height="169" alt="Screenshot 2026-03-16 202841" src="https://github.com/user-attachments/assets/6b720354-9ada-4a7a-9333-89ee8942400b" />


Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.
```

@echo off
:menu
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
set /p choice=Choose an option: 
if "%choice%"=="1" goto hello
if "%choice%"=="2" goto createfile
if "%choice%"=="3" goto end

:hello
echo Hello, World!
goto menu

:createfile
echo Creating a file...
echo This is a new file > newfile.txt
goto menu
:end
echo Goodbye!
pause

```
## OUTPUT

<img width="640" height="504" alt="Screenshot 2026-03-16 202950" src="https://github.com/user-attachments/assets/433a662c-43e9-4342-bcd5-5c782edd0ad0" />


# RESULT:
The commands/batch files are executed successfully.


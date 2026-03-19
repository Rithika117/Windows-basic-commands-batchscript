# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript
 
# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file
Save each script in a file with a .bat extension.
Ensure you have the necessary permissions to perform the operations.
Adapt paths as needed based on your system configuration.
### Step 3:

Execute the necessary commands/batch file for the desired output. 




# WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations
Create a directory named "MyLab" on the desktop.


## COMMAND AND OUTPUT

```
mkdir %userprofile%\Desktop\MyLab
```
![1_mkdir](https://github.com/user-attachments/assets/b2c97dd3-0863-4481-8a62-027ad75b56f0)


Change to the "MyLab" directory and create an empty text file named "MyFile.txt" inside it.


## COMMAND AND OUTPUT

```
cd %userprofile%\Desktop\MyLab
```
![2_cd](https://github.com/user-attachments/assets/4749e48a-d6c2-465c-b66c-467b535e741c)


type nul > MyFile.txt
![3_myfile](https://github.com/user-attachments/assets/264f09a9-9ab1-4319-8ffb-087580360d88)


List the contents of the "MyLab" directory.


## COMMAND AND OUTPUT

```
dir %userprofile%\Desktop\MyLab
```
![4_dir](https://github.com/user-attachments/assets/8a095fc7-fb1e-4b82-9dff-46ed48ac79c9)

Copy "MyFile.txt" to a new folder named "Backup" on the desktop.

## COMMAND AND OUTPUT

```
mkdir %userprofile%\Desktop\Backup
```
![5_backup](https://github.com/user-attachments/assets/40881217-36a6-4c3b-9a98-084c1d4f06b7)

copy MyFile.txt %userprofile%\Desktop\Backup

![6_copy](https://github.com/user-attachments/assets/15c04a42-8b5e-4005-a4d6-eefff8a529c2)

Move the "MyLab" directory to the "Documents" folder.

## COMMAND AND OUTPUT

```
mkdir %userprofile%\Desktop\Documents
```
move MyLab Documents

![9_modified batch1](https://github.com/user-attachments/assets/6db49bc8-0724-45f1-a9f3-ff9ef8d5ffbf)

## Exercise 2: Advanced Batch Scripting
Create a batch script named "BackupScript.bat" that creates a backup of files with the ".docx" extension from the "Documents" folder to a new folder named "DocBackup" on the desktop.

## COMMAND

```
@echo off
mkdir %userprofile%\Desktop\DocBackup
copy %userprofile%\Documents\*.docx %userprofile%\Desktop\DocBackup
echo Backup completed successfully!
```

## OUTPUT

![10_batch1](https://github.com/user-attachments/assets/af5e3830-2b8c-465d-9ccb-b6c15b159502)

## COMMAND
```
  @echo off
  mkdir %userprofile%\Desktop\DocBackup
  copy %userprofile%\Documents\*.docx %userprofile%\Desktop\DocBackup
  del %userprofile%\Documents\*.docx
  echo Backup and deletion completed successfully!
```
## OUTPUT

![11_modified batch1](https://github.com/user-attachments/assets/db602c4e-116e-4c0c-84d3-9e750b2d6ebe)

# RESULT:
The commands/batch files are executed successfully.


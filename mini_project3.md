# Linux Files and Directory Manipulation Project

**Date:** 2025-04-19  
**Objective:** Learn and practice fundamental Linux commands for file and directory manipulation.

---

## 1. Using `sudo` to Create a Folder in Restricted Area

```bash
mkdir /root/example      # Expected to fail (Permission denied)
sudo mkdir /root/example  # Should succeed
sudo ls /root             # Verify the directory exists
```
<img width="896" alt="Image" src="https://github.com/user-attachments/assets/11ea664f-dee1-4316-b61e-259afd50d9f8" />
## 2. Navigating the Filesystem

```bash
pwd          # Print current directory
cd /usr      # Navigate to /usr
ls -la       # List all files with details
```
<img width="596" alt="Image" src="https://github.com/user-attachments/assets/6a16c057-9658-4949-8581-ea220e12df52" />
## 3. Creating Directories

```bash
sudo mkdir /usr/photos           # Create 'photos' directory
cd /usr/photos                   # Navigate into it
mkdir img1 img2 img3             # Create 3 directories inside 'photos'
cd img1                          # Navigate into one of them
pwd                              # Show full path
```
<img width="839" alt="Image" src="https://github.com/user-attachments/assets/1b73587a-2f47-409f-8410-6e29eea3ec05" />
## 4. Viewing File Content with `cat`

```bash
cat /etc/os-release              # Show OS information
```
<img width="686" alt="Image" src="https://github.com/user-attachments/assets/9441f260-cf57-4850-aa31-6ca952fc376f" />
## 5. Copying Files

```bash
cp file1.txt /home/ubuntu/Documents/
cp file1.txt file2.txt file3.txt /home/ubuntu/Documents/
cp -R /home/ubuntu/Documents /home/ubuntu/Documents_backup
```
<img width="876" alt="Image" src="https://github.com/user-attachments/assets/b1e23289-a62b-487f-a2b8-9cb9609170d4" />
## 6. Moving and Renaming Files

```bash
mv file1.txt /home/ubuntu/Documents/
mv old_name.txt new_name.txt     # Renaming a file
```
<img width="754" alt="Image" src="https://github.com/user-attachments/assets/70a172f7-dc23-488f-b8dd-92e831536d7b" />
## 7. Deleting Files and Directories

```bash
rm filename                      # Delete a single file
rm file1.txt file2.txt           # Delete multiple files
rm -r directory_name             # Delete a directory
```
<img width="751" alt="Image" src="https://github.com/user-attachments/assets/4369ec55-cbb0-4558-a5cc-93323c832328" />
## 8. Creating Files with `touch`

```bash
touch /home/ubuntu/Documents/Web.html   # Create an empty HTML file
```
<img width="583" alt="Image" src="https://github.com/user-attachments/assets/37bdd52e-8f83-478b-b232-6042fac1812d" />
## 9. Searching with `find`

```bash
find /home -name notes.txt       # Find a specific file
```

---
<img width="953" alt="Image" src="https://github.com/user-attachments/assets/58604f3b-fc7d-47d3-9e9e-486730b2f3a6" />
**Note:** Always use `sudo` with caution, especially when manipulating system directories or files.


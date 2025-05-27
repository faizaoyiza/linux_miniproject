# **File Permissions and Access Rights in Linux**

Understanding how to manage file permissions and ownership is crucial in Linux. This ensures that only authorized users can access, modify, or execute files and directories—safeguarding system security and integrity.

---

## **1. File Permissions Overview**

In Linux, each file and directory has three permission types for three categories of users:

- **User (owner)**
- **Group**
- **Others**

Each permission type includes:

- **r (read)** – permission to view contents  
- **w (write)** – permission to modify contents  
- **x (execute)** – permission to run the file (if it's a script/program)

---

## **2. Numeric Representation of Permissions**

Permissions are represented as numbers:
- `read` = 4  
- `write` = 2  
- `execute` = 1

These values are added together to get a single number for each user class.

### Examples:

| Numeric | Symbolic | Meaning                              |
|---------|----------|--------------------------------------|
| 7       | rwx      | Read, write, and execute             |
| 6       | rw-      | Read and write only                  |
| 5       | r-x      | Read and execute only                |
| 0       | ---      | No permissions                       |

**Example:**  
`chmod 755 filename`  
Means:
- User: 7 → `rwx`  
- Group: 5 → `r-x`  
- Others: 5 → `r-x`

---

## **3. Symbolic Representation of Permissions**

Each file or directory has a 10-character string representation like:

```
-rwxr-xr-x
```

Explanation:
- `-` → regular file (`d` for directory)
- `rwx` → user permissions
- `r-x` → group permissions
- `r-x` → others' permissions

---

## **4. Common Commands**

### **`ls -latr`**  
Lists files with detailed permission info.

### **Creating Files**
```bash
touch script.sh
ls -latr script.sh
```
Example output:
```
-rw-r--r-- 1 user group 0 Jul 6 23:38 script.sh
```
<img width="949" alt="Image" src="https://github.com/user-attachments/assets/1dd8edd1-7eee-49ca-84d6-3d249e4cf75b" />
Interpretation:
- User: `rw-` → read & write  
- Group: `r--` → read-only  
- Others: `r--` → read-only

### **chmod – Change File Permissions**
- Add execute permissions to all:
  ```bash
  chmod +x script.sh
  ```
- Numeric method:
  ```bash
  chmod 755 script.sh
  ```

### **chown – Change Ownership**
Syntax:
```bash
chown user:group filename
```

Example:
```bash
chown john:developers filename.txt
```

---
<img width="939" alt="Image" src="https://github.com/user-attachments/assets/c7471b6d-8c43-4de9-8e05-2f8111c8704b" />
## **5. Superuser Privileges (`sudo`)**

To temporarily gain superuser rights:
```bash
sudo command
```

To switch to the root user:
```bash
sudo -i
```

To exit:
```bash
exit
```

---
<img width="728" alt="Image" src="https://github.com/user-attachments/assets/f24025a3-ea41-477c-9778-7f66f0ffde70" />
## **6. User Management**

### **Create a New User**
```bash
sudo adduser johndoe
```

### **Grant Admin Rights**
```bash
sudo usermod -aG sudo johndoe
```

### **Switch User**
```bash
su johndoe
```

### **Change Password**
```bash
sudo passwd johndoe
```

---
<img width="866" alt="Image" src="https://github.com/user-attachments/assets/11bc5dba-627e-4824-96c6-30f7ab49221b" />
## **7. Group Management**

### **Create a Group**
```bash
sudo groupadd developers
```

### **Add User to Group**
```bash
sudo usermod -aG developers johndoe
```

### **Check Group Membership**
```bash
id johndoe
```

### **Set Group Ownership of a Directory**
```bash
sudo chown :developers /path/to/directory
```

### **Grant Group Permissions**
```bash
sudo chmod g+rw /path/to/directory
```

---
<img width="907" alt="Image" src="https://github.com/user-attachments/assets/35ca6103-4701-4054-80c8-1c923e552276" />
## **8. Task: DevOps Group Setup**

### **Create Group**
```bash
sudo groupadd devops
```

### **Create Users and Add to Group**
```bash
for user in mary mohammed ravi tunji sofia
do
  sudo adduser $user
  sudo usermod -aG devops $user
done
```

### **Create Home Folders and Set Group Ownership**
```bash
for user in mary mohammed ravi tunji sofia
do
  sudo mkdir /home/$user
  sudo chown $user:devops /home/$user
  sudo chmod 770 /home/$user
done
```
<img width="910" alt="Image" src="https://github.com/user-attachments/assets/df03f227-0588-4cb1-abae-6ac3fd43284e" />


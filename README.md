# linux_miniproject
# create an EC2 instance
<img width="955" alt="Image" src="https://github.com/user-attachments/assets/79e40441-b674-49bb-b676-e904f8b13bd9" />
# 🌐 Cloud Server & Nginx Setup Project

This project involves provisioning a cloud server (e.g., on AWS), connecting via SSH, installing packages using a package manager, and running a web server (Nginx).

---

## 🧩 Project Steps

### 1. 🔐 Connect to the Server Using SSH

```bash
cd /drives/C/Users/Abdul/Downloads  # Navigate to where the .pem key is stored

ssh -i "key.pem" ubuntu@<your-public-ip>  # Replace <your-public-ip> with your real server IP
```

> Example:  
> `ssh -i "key.pem" ubuntu@51.20.34.142`

---
<img width="773" alt="Image" src="https://github.com/user-attachments/assets/daee1a2c-2814-453f-bee2-d8e06fa3f5ee" />
### 2. 📦 Update & Install Required Packages

#### Update system packages:

```bash
sudo apt update
```
<img width="625" alt="Image" src="https://github.com/user-attachments/assets/f3ae3eef-ecf0-4ce0-9ef1-54227ff5a5ea" />
#### Install `tree` (for visualizing file structure):

```bash
sudo apt install tree
tree ~
```

---
<img width="758" alt="Image" src="https://github.com/user-attachments/assets/e370a323-3515-4b56-beed-c622e11080ae" />
### 3. 🚀 Install & Start Nginx Web Server

#### Install Nginx:

```bash
sudo apt install nginx
```
<img width="683" alt="Image" src="https://github.com/user-attachments/assets/7737e013-de80-4bbb-a378-34920b21a355" />
#### Start the Nginx service:

```bash
sudo systemctl start nginx
```

#### Check Nginx status:

```bash
sudo systemctl status nginx
```

> If Nginx is running, you should see: `Active: active (running)`

---
<img width="761" alt="Image" src="https://github.com/user-attachments/assets/5c3e63eb-d31d-43b5-95c4-db2084ed1765" />
### 4. ✅ Test the Web Server

#### From inside the server:

```bash
curl http://localhost
```
<img width="729" alt="Image" src="https://github.com/user-attachments/assets/84b9a111-41dd-4ee4-b930-f7ccbb1860a9" />
#### From a browser:
Go to:  
**`http://<your-public-ip>`**

> Example: [http://51.20.34.142](http://51.20.34.142)

You should see the default **"Welcome to Nginx"** page.

---


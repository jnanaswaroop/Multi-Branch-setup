# Multi-Branch Pipeline Setup

This repository is created specifically for **Jenkins Multibranch Pipeline Setup Practical**.  
You can use this repo during your CI/CD learning, YouTube tutorials, or demo sessions to showcase how Jenkins automatically discovers and builds multiple branches using a single repository.

---

## 📌 What This Repository Demonstrates

- How Jenkins **Multibranch Pipeline** works  
- Automatic **branch discovery**  
- Separate builds for **main, dev, feature** branches  
- How Jenkins reads **Jenkinsfile per branch**  
- How Docker images can be built uniquely per branch  
- Practical setup for CI/CD demonstration on your YouTube channel  

---

## 📁 Repository Structure

```
Multi-Branch-setup-main/
│── Jenkinsfile
│── branch_docker_images.sh
│── folder1/
│     └── file1.txt
│── folder2/
      └── file2.txt
```

### ✔️ Jenkinsfile  
Defines pipeline stages:
- SCM Checkout  
- Docker Build  
- Docker Tag Based on Branch  
- Docker Push  
- Post Actions  

### ✔️ branch_docker_images.sh  
Shell script that:
- Detects branch  
- Builds Docker image  
- Tags image as:  
  ```
  myapp:<branch-name>
  ```
- Pushes to registry  

---

## 🏗️ How to Use This Repo for Jenkins Multibranch Pipeline

### **Step 1: Create a Multibranch Pipeline**
- Go to Jenkins → *New Item*
- Select **Multibranch Pipeline**
- Enter job name (e.g., *multi-branch-setup-demo*)

### **Step 2: Add GitHub Repository URL**
- Under *Branch Sources → Git*  
- Add repo URL  
- Add credentials if private

### **Step 3: Configure Build Triggers**
Enable:
- **Periodic Scans**  
- **Webhook Trigger From GitHub** for real-time builds

### **Step 4: Jenkins Auto-Discovers Branches**
You will see jobs like:

```
main
dev
feature/test
```

Each branch gets its own pipeline.

---

## 🧪 Branch Testing

Make multiple branches:
```
main
dev
feature/test
```

Edit Jenkinsfile or code inside each branch → Commit → Push  
Jenkins will auto-build each branch independently.

---

## 🚀 Expected Jenkins Output

### Example Docker Tags:
```
myapp:main
myapp:dev
myapp:feature-test
```

### Example Jenkins Job List:
```
Multi-Branch-Demo » main
Multi-Branch-Demo » dev
Multi-Branch-Demo » feature-test
```

---

## 🎥 Follow the Tutorial on YouTube

These repositories and setups are used for practical demos on my YouTube channel.  
You can follow along here:

### 🔗 YouTube Channel  
**DevOps With Shubham Gour**  
[https://www.youtube.com/@shubhamgourtech](https://www.youtube.com/shubhamgourtech)  



---

## 📌 Notes

- Ensure Docker is installed on Jenkins agent  
- Add DockerHub credentials in Jenkins  
- Enable GitHub webhook for auto-trigger  
- Jenkinsfile must exist at root of every branch

---

## 🙌 Author  
Created by **Shubham Gour**  
For DevOps, Release Engineering, and CI/CD learners.


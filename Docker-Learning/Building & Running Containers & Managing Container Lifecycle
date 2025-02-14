## **🚀 Building & Running Containers & Managing Container Lifecycle**  

### **1️⃣ Building & Running Containers**
Once we have a **Dockerfile**, we need to build an image and run a container from it.

#### **🛠️ Building a Docker Image**
```sh
docker build -t my-app .
```
🔹 `docker build` → Creates a Docker image.  
🔹 `-t my-app` → Tags the image with the name `my-app`.  
🔹 `.` → Refers to the current directory (where the Dockerfile is located).  

---

#### **🚀 Running a Container from an Image**
```sh
docker run -d -p 5000:5000 my-app
```
🔹 `docker run` → Starts a new container.  
🔹 `-d` → Runs the container in detached mode (in the background).  
🔹 `-p 5000:5000` → Maps **port 5000 of the container** to **port 5000 of the host machine**.  
🔹 `my-app` → The name of the image to run.  

**📌 Example Use Case:**  
If you have a web application running on port `5000` inside the container, it will now be accessible on `http://localhost:5000`.

---

### **2️⃣ Managing the Container Lifecycle**
Once the container is running, we can manage it using various commands.

#### **🔄 Restarting a Container**
```sh
docker restart <container_id_or_name>
```
🔹 Restarts a running container.  
🔹 Useful if you make changes to configurations and want to apply them.

---

#### **💻 Executing Commands Inside a Running Container**
```sh
docker exec -it <container_id_or_name> bash
```
🔹 `docker exec` → Runs a command inside a container.  
🔹 `-it` → Interactive mode (keeps terminal open).  
🔹 `bash` → Opens a bash shell inside the container.  
**Example:**
```sh
docker exec -it my-app bash
```
Now, you are inside the container and can run commands like:
```sh
ls /app
python3 app.py
```
To exit, type `exit`.

---

#### **🔎 Inspecting a Container**
```sh
docker inspect <container_id_or_name>
```
🔹 Shows detailed information about the container, including:  
  - Environment variables  
  - Mounted volumes  
  - Network settings  

**Example:**
```sh
docker inspect my-app
```

---

#### **📂 Copying Files Between Host and Container**
```sh
docker cp <container_id>:<path_in_container> <path_on_host>
```
🔹 Copies files from **container → host**.  

**Example:**
```sh
docker cp my-app:/app/logs.txt ./logs.txt
```
🔹 Copies `logs.txt` from `/app/` in the container to your local machine.

```sh
docker cp ./config.json my-app:/app/config.json
```
🔹 Copies `config.json` from your host to `/app/` inside the container.

---

### **✅ Summary**
- `docker build -t my-app .` → Creates an image.  
- `docker run -d -p 5000:5000 my-app` → Runs a container.  
- `docker restart my-app` → Restarts a running container.  
- `docker exec -it my-app bash` → Access container shell.  
- `docker inspect my-app` → View detailed container info.  
- `docker cp` → Copy files **between** host and container.  

Would you like to try a **hands-on exercise** or move to **Volumes & Persistent Data** next? 🚀

# **Basic Docker Commands & Usage** 🐳  

These essential Docker commands will help you **run, manage, and inspect containers** efficiently.

---

## **1️⃣ `docker run` → Start a container** 🚀  
### **Usage:**  
Creates and starts a new container from an image. If the image isn’t available locally, it pulls it from **Docker Hub**.  

### **Syntax:**  
```sh
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```
### **Common Options:**
| Option | Description |
|--------|------------|
| `-d` | Run container in **detached mode** (background) |
| `-it` | Run in **interactive mode** (useful for debugging) |
| `--name mycontainer` | Assigns a **custom name** to the container |
| `-p 8080:80` | Maps **host port** to container port |
| `-v myvolume:/data` | Attaches a **volume** for persistent storage |

### **Examples:**
1️⃣ **Run an Nginx server in the background**  
```sh
docker run -d -p 8080:80 --name mynginx nginx
```
Now, open **http://localhost:8080** in your browser.  

2️⃣ **Run an interactive Ubuntu container**  
```sh
docker run -it ubuntu bash
```
This opens a shell inside the Ubuntu container. Type `exit` to quit.  

---

## **2️⃣ `docker ps` → List running containers** 📋  
### **Usage:**  
Shows all currently running containers.  

```sh
docker ps
```
### **Output Example:**
```
CONTAINER ID   IMAGE    STATUS         PORTS           NAMES
a1b2c3d4e5f6   nginx    Up 5 minutes   0.0.0.0:8080->80/tcp   mynginx
```
| Column | Description |
|--------|------------|
| **CONTAINER ID** | Unique ID for the container |
| **IMAGE** | The image from which the container was started |
| **STATUS** | Whether the container is running, paused, or stopped |
| **PORTS** | Shows port mappings |
| **NAMES** | Auto-assigned or user-defined name |

### **Show all containers (including stopped ones):**  
```sh
docker ps -a
```

---

## **3️⃣ `docker stop` → Stop a running container** ⏹️  
### **Usage:**  
Gracefully stops a running container.  

```sh
docker stop mynginx
```
OR using the **Container ID**:  
```sh
docker stop a1b2c3d4e5f6
```
🔹 If you need to **force-stop** a container:  
```sh
docker kill mynginx
```

---

## **4️⃣ `docker rm` → Remove a container** 🗑️  
### **Usage:**  
Deletes a stopped container.  

```sh
docker rm mynginx
```
🔹 **Remove all stopped containers** in one go:  
```sh
docker container prune
```

⚠️ **You cannot remove a running container!** Stop it first using `docker stop`.

---

## **5️⃣ `docker logs` → View container logs** 📜  
### **Usage:**  
Shows logs (output) of a running or stopped container.  

```sh
docker logs mynginx
```
🔹 **Follow logs in real time (like `tail -f`)**  
```sh
docker logs -f mynginx
```
🔹 **Show last 10 lines of logs**  
```sh
docker logs --tail 10 mynginx
```

---

## **📝 Summary Table**  
| Command | Usage |
|---------|-------|
| `docker run -d -p 8080:80 --name mynginx nginx` | Start an Nginx container in the background |
| `docker ps` | List running containers |
| `docker ps -a` | List all containers (running + stopped) |
| `docker stop mynginx` | Stop a running container |
| `docker rm mynginx` | Remove a stopped container |
| `docker logs mynginx` | View logs of a running container |

---

🚀 **Next Steps:** Want to learn about managing images (`docker images`, `docker rmi`) or working with volumes and networks? Let me know!

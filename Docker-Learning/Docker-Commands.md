### **📜 List of Docker Commands You Have Learned So Far**  

#### **1️⃣ Basic Docker Commands**  
- `docker run <image>` → Runs a container from an image  
- `docker ps` → Lists running containers  
- `docker ps -a` → Lists all containers (including stopped ones)  
- `docker stop <container-id>` → Stops a running container  
- `docker rm <container-id>` → Removes a stopped container  
- `docker logs <container-id>` → Shows logs of a container  

#### **2️⃣ Building & Managing Images**  
- `docker build -t <image-name> .` → Builds an image from a `Dockerfile`  
- `docker images` → Lists all available images  
- `docker pull <image-name>` → Pulls an image from Docker Hub  
- `docker rmi <image-name>` → Removes an image  
- `docker commit <container-id> <new-image-name>` → Creates an image from a running container  

#### **3️⃣ Running & Managing Containers**  
- `docker run -it <image> <command>` → Runs a container interactively  
- `docker run -d <image>` → Runs a container in detached mode  
- `docker run --rm <image>` → Runs a container and removes it after exit  
- `docker start <container-id>` → Starts a stopped container  
- `docker restart <container-id>` → Restarts a container  
- `docker stop <container-id>` → Stops a running container  
- `docker kill <container-id>` → Kills a container immediately  

#### **4️⃣ Working with Volumes & Networks (Coming Soon)**  
- `docker volume create <volume-name>` → Creates a volume  
- `docker network create <network-name>` → Creates a network  

---

This covers everything you've learned so far. Do you want to practice more or move on to **Container Lifecycle Management**? 🚀

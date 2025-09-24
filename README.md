# working_with_docker_images
### 🐳 **Docker Images – What They Are**

A Docker image is like a **blueprint** for a container. It’s a lightweight, read-only package that includes everything an application needs to run: code, libraries, dependencies, and configuration. Containers are simply running instances of these images.

---

### 🔧 **Basic Operations with Docker Images**

1. **Pull an image (download from Docker Hub or registry):**

   ```bash
   docker pull nginx:latest
   ```
   Downloads the official Nginx image.

2.  **List available images on your system:**

   ```bash
   docker images
   ```
   -------------------------------------------------------------------------------------------------------
   lets cconnect to an ec2 instance with ubuntu ami. we shall demo docker pull, docker images, and docker ps.
  <img width="946" height="389" alt="image" src="https://github.com/user-attachments/assets/450c438c-3d92-477e-9b10-c9a6fec6659b" />
  <img width="962" height="503" alt="image" src="https://github.com/user-attachments/assets/0928085a-1c81-4026-9eb7-8d6fe43a784b" />
  <img width="961" height="515" alt="image" src="https://github.com/user-attachments/assets/8a6bd22d-68a5-4b12-b1b2-e1b03d4f703f" />

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------




3. **Build your own image (using a Dockerfile):**

   ```bash
   docker build -t myapp:1.0 .
   ```

   * `-t` tags the image with a name and version.
   * `.` means build from the Dockerfile in the current directory.
  
    --------------------------------------------------------------------------------------------------------------------------
lets create a dockerfile and enter the commands we want our nginx image to be built with. 
<img width="959" height="187" alt="image" src="https://github.com/user-attachments/assets/b149df43-db5c-4158-acc9-aa1b8808d385" />
<img width="959" height="513" alt="image" src="https://github.com/user-attachments/assets/9d53a3e5-4960-49d5-ae9f-1e9a9aeb1c80" />
<img width="959" height="127" alt="image" src="https://github.com/user-attachments/assets/efcef24b-6abd-4a8d-8689-68c48e7428f3" />
<img width="963" height="328" alt="image" src="https://github.com/user-attachments/assets/375f1b7c-bbb9-4540-8ba1-a544268297c0" />
<img width="963" height="328" alt="image" src="https://github.com/user-attachments/assets/1889bb73-5a12-4d63-af15-3183b417ac6a" />
<img width="962" height="386" alt="image" src="https://github.com/user-attachments/assets/9e73bbb3-aa9e-4c36-8da7-450d72cc3476" />
------------------------------------------------------------------------------------------------------------------------------------------------

4. **Run a container from an image:**

   ```bash
   docker run -d -p 8080:80 nginx
   ```

   * `-d` runs it in detached mode.
   * `-p` maps port 8080 on your machine to port 80 in the container.
  
     -------------------------------------------------------------------------------------------------------
     lets run a conatiner from the image dockerfile.
     <img width="953" height="466" alt="image" src="https://github.com/user-attachments/assets/62caf27b-8940-47e6-ba78-4be94cc9a750" />

     because the port 8080 was mapped to nginx port 80, we have to edit the security group to channel traffic through port 8080.
     <img width="946" height="398" alt="image" src="https://github.com/user-attachments/assets/321e20b8-1099-4ad9-ac6e-8b7a137771f8" />
     <img width="943" height="374" alt="image" src="https://github.com/user-attachments/assets/6572ba01-2201-4eea-a54b-1ab558e3a44b" />
     <img width="935" height="378" alt="image" src="https://github.com/user-attachments/assets/3e8b9681-d21f-4d66-9a8d-e88bcf95ab3b" />
     <img width="466" height="101" alt="image" src="https://github.com/user-attachments/assets/8ae773fb-7ed4-4b86-97b5-b3457bd23092" />

     ---------------------------------------------------------------------------------------------------------------------------------------


     



6. **Tag and push image to a registry (e.g., Docker Hub):**

   ```bash
   docker tag myapp:1.0 mydockerhubusername/myapp:1.0
   docker push mydockerhubusername/myapp:1.0
   ```

7. **Remove an image (cleanup):**

   ```bash
   docker rmi myapp:1.0
   ```

---

### 🎯 **Why Docker Images Are Useful**

* **Consistency** → Works the same in dev, test, and production.
* **Portability** → You can move images across machines or clouds.
* **Reusability** → Share pre-built images (e.g., MySQL, Node.js).
* **Efficiency** → Layers reduce duplication and speed up builds.



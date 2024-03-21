![1_uuZ-h5EH76LOtJ614z-qDA](https://github.com/rishusam/Host-web-app-in-Docker-Container/assets/113242832/369aecb8-d8a8-4063-8304-bea77bfa61f3)
# Host-web-app-in-Docker-Container
hosting an web app on docker container using AWS aubantu Vm machine
To create a web app container on Docker using an AWS Ubuntu instance, you'll need to follow these general steps:

1. **Set up an AWS EC2 Ubuntu instance**: Launch an Ubuntu instance on AWS EC2. Make sure to open the necessary ports for your web app.

2. **SSH into your Ubuntu instance**: Use SSH to connect to your Ubuntu instance.

3. **Install Docker**: Update your package index and install Docker on your Ubuntu instance.

4. **Create your web app**: Write your web application code (e.g., HTML, CSS, JavaScript, etc.) and any necessary dependencies.

5. **Create a Dockerfile**: In your project directory, create a `Dockerfile` specifying the instructions to build your Docker image.

6. **Build your Docker image**: Use the `docker build` command to build your Docker image based on the `Dockerfile`.

7. **Run your Docker container**: Once the image is built, use the `docker run` command to run your container.

Here's a very basic example to get you started:

### 1. Set up an AWS EC2 Ubuntu instance:
Launch an AWS EC2 instance with Ubuntu, ensuring that you have the necessary security groups to allow inbound traffic on the ports your web app will use (e.g., port 80 for HTTP).

### 2. SSH into your Ubuntu instance:
Use SSH to connect to your Ubuntu instance:

```bash
ssh -i your-key.pem ubuntu@your-instance-public-ip
```

### 3. Install Docker:
Update your package index and install Docker on your Ubuntu instance:

```bash
sudo apt update
sudo apt install docker.io
```

### 4. Create your web app:
Create your web application code (e.g., a simple HTML file) and place it in a directory on your Ubuntu instance.

### 5. Create a Dockerfile:
Create a `Dockerfile` in the same directory as your web app files:

```Dockerfile
# Use an official Nginx image as the base image
FROM nginx:latest

# Copy the web app files into the Nginx HTML directory
COPY . /usr/share/nginx/html
```

### 6. Build your Docker image:
Navigate to the directory containing your `Dockerfile` and run the following command to build your Docker image:

```bash
docker build -t my-web-app .
```

### 7. Run your Docker container:
Once the image is built, you can run your Docker container using the following command:

```bash
docker run -d -p 80:80 my-web-app
```

This will run your web app container in detached mode, mapping port 80 of the container to port 80 of the host (your AWS instance).

Your web app should now be accessible via the public IP address of your AWS instance.

it & Directory Commands

git clone <repo-url>

     Clones a remote Git repository to your local machine.

cd <folder-name>

    Navigates into the specified directory.

🐳 Dockerfile Instructions

     FROM nginx:alpine
     Specifies the base image to use (here, lightweight Nginx on Alpine Linux).


RUN 

     rm -rf /usr/share/nginx/html/*
    Executes a command inside the image during the build process.


COPY . 

    /usr/share/nginx/html
    Copies files from your host machine into the image's filesystem.

EXPOSE 80

    Documents that the container listens on port 80 at runtime.

⚙️ Docker CLI Commands

    docker build -t food-app .

    Builds a Docker image from the Dockerfile in the current directory and names it food-app.

docker run -d -p 8080:80 --name 

    food-app-container food-app

    Runs the food-app image in detached mode, mapping host port 8080 to container port 80.
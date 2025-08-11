### 🚀Multi-Stage Docker Images & Containers | Application Deployment

Multi-stage Dockerfile is an essential feature provided by Docker that allows developers to create more efficient and smaller Docker images, resulting in faster builds, reduced image sizes, and improved security.

 #### 📌**Benefits & Importance of Multi-Stage Builds**
   
   - Reduced Image Size
   - Faster Build Times
   - Improved Security
   - Simplified Build Pipeline
   - Portability and Consistency


Here is the real example of Multi-Stage Dockerfile. We converted [Single-Stage Dockerfile](https://github.com/saifulislam88/docker/blob/main/A.docker-principle-concept/introduction-docker-container.md#write-a-dockerfile-on-nodejs-application) to Multi-Stage Dockerfile in below.

#### **Find the following Multi-Stage Dockerfile**
```sh
# Stage 1: Build
FROM node:14 as build

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy the package.json and package-lock.json files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Stage 2: Production
FROM node:14-slim

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy only the necessary files from the build stage
COPY --from=build /usr/src/app .

# Make port 3000 available to the world outside this container
EXPOSE 3000

# Run the app
CMD ["node", "app.js"]

```
-  #### 📌**How It Works**

   - **Build Stage**

      - The first stage (`build`) uses the `node:14` image to set up the build environment.
      - It sets the working directory, copies the `package.json` and `package-lock.json` files, and installs the dependencies using `npm install`.
      - It then copies the rest of the application code.

   - **Production Stage:**

      - The second stage (`production`) uses a lighter `node:14-slim` image, which is smaller and optimized for production use.
      - It sets the working directory and copies the necessary files from the `build` stage using `COPY --from=build`.
      - It exposes port `3000` and specifies the command to run the application.

  - #### 📌Compare Single-Stage Image vs Muti-Stage Image
  
`docker image ls`

  - #### 📌Build an Image: Use the Dockerfile to build a Docker image & Run from local Image - Multi-Stage 

`docker build -t my-node-app .`

`docker run -it -d -p 3000:3000 my-node-app

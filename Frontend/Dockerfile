# Stage 1: Build
FROM node:20.13.1 AS build

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install any needed packages
RUN npm install

# Copy the rest of the application code
COPY . .

# Build the application (add this line for frontend frameworks)
RUN npm run build  # Change this command if your build command is different

# Stage 2: Serve
FROM nginx:alpine

# Copy the build output to Nginx's html directory
COPY --from=build /usr/src/app/build /usr/share/nginx/html

# Expose the port the app runs on
EXPOSE 80

# Define the command to run Nginx
CMD ["nginx", "-g", "daemon off;"]

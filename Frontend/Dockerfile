# Use an official Node.js runtime as a parent image
FROM node:20.13.1

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install only production packages for smaller image size
RUN npm install --production

# Copy the rest of the application code
COPY . .

# Set environment variable for the port
ENV PORT=3000

# Expose the port the app runs on
EXPOSE 3000

# Define the command to run the app
CMD ["npm", "start"]

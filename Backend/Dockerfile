# Use a Node.js image
FROM node:14 AS build

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install all dependencies
RUN npm install

# Copy the rest of the backend code
COPY . .

# Build the application (add this line if your app needs a build step)
RUN npm run build  # Make sure you have a "build" script in your package.json

# Production stage
FROM node:14

# Set the working directory
WORKDIR /app

# Copy only the necessary files from the build stage
COPY --from=build /app .

# Install only production dependencies
RUN npm install --production

# Expose the port the app listens on
EXPOSE 5000

# Start the server
CMD ["npm", "start"]

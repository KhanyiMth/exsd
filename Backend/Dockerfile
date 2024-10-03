# Use a Node.js image
FROM node:14

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install --production  # Use --production to skip dev dependencies in production

# Copy the rest of the backend code
COPY . .

# Expose the port the app listens on
EXPOSE 5000

# Start the server
CMD ["npm", "start"]

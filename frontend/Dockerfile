# Use the official Node.js image from the Docker Hub
FROM node:20-slim

# Set the working directory in the container
WORKDIR /app

# Copy the package.json and package-lock.json first
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application files
COPY . .

# Build the app for production
RUN npm run build

# Start the app using the Vite preview command
CMD npm run dev -- --host 0.0.0.0

# Use an official Node.js runtime as a parent image
FROM node:18

# Set the working directory in the container
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install app dependencies
RUN npm install

# Copy the rest of the application code to the working directory
COPY . .

# Build the React app (if needed)
RUN npm run build

# Install 'serve' globally
RUN npm install -g serve

# Expose the port on which your React app will run (e.g., 3000)
EXPOSE 9000

# Serve the build files when the container starts
CMD ["serve", "-s", "build", "-l", "9000"]

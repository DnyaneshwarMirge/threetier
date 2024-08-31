# Use an official Node.js runtime as a parent image
FROM node:14

# Set the working directory in the container
WORKDIR /app

# Copy the package.json and install dependencies
COPY package*.json ./
RUN npm install

# Copy the rest of the application code
COPY . .

# Expose the port on which the app will run
EXPOSE 3000

# Define environment variable (Adjust according to your setup)
ENV REACT_APP_SERVER_URL=http://backend:8080/employees

# Build the React app
RUN npm run build

# Serve the app using a simple static server
RUN npm install -g serve
CMD ["serve", "-s", "build"]

# Use an official Node.js runtime as the base image
FROM node:14

# Set the working directory in the container to /21i_1105_backend
WORKDIR /21i_1105_backend

# Copy package.json and package-lock.json to the working directory
COPY package.json ./

# Install the application dependencies
RUN npm install

# Copy the rest of the application code to the working directory
COPY . .

# Make port 3105 available to the outside world
EXPOSE 3105

# Define the command to run the application
CMD [ "npm", "start" ]
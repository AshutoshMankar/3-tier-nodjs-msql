FROM node:14-alpine

# Set the working directory in the container for the client
WORKDIR /usr/src/app/client

# Copy package.json and package-lock.json
COPY client/package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the client application
COPY client/ ./

# Set correct permissions
RUN chmod -R 755 node_modules/.bin

# Build the client application
RUN npm run build

# Set the working directory in the container for the server
WORKDIR /usr/src/app/server

# Copy package.json and package-lock.json
COPY server/package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the server application
COPY server/ ./

# Expose the port the app runs on
EXPOSE 3000

# Start the application
CMD ["npm", "start"]

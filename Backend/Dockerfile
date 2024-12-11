# Use Node.js image
FROM node:16

# Set working directory
WORKDIR /app

# Copy package.json and package-lock.json, then install dependencies
COPY package*.json ./
RUN npm install

# Copy all source code
COPY . .

# Expose the backend API port
EXPOSE 5000

# Start the backend application
CMD ["npm", "start"]

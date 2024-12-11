# Build the frontend
FROM node:16 AS build
WORKDIR /app

# Copy package files and install dependencies
COPY package*.json ./
RUN npm install

# Copy the source code
COPY . .

# Run the build command (Vite outputs to /app/dist by default)
RUN npm run build

# Serve the frontend with nginx
FROM nginx:stable-alpine
WORKDIR /usr/share/nginx/html

# Copy the production build files to nginx
COPY --from=build /app/dist /usr/share/nginx/html

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]

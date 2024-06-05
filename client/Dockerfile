# Build stage
FROM node:14 AS build
# Set the working directory
WORKDIR /21i_1105_frontend
# Copy package.json and package-lock.json
COPY package.json ./
# Install dependencies
RUN npm install
# Copy the rest of the code
COPY . .
# Build the application
RUN npm run build

# Production stage
FROM nginx:stable-alpine AS production
# Copy the build output to replace the default nginx contents.
COPY --from=build /21i_1105_frontend/build /usr/share/nginx/html
# Expose port 1105
EXPOSE 1105
# Start Nginx
CMD ["nginx", "-g", "daemon off;"]
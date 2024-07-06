# Use an official Node.js 14.x image as the base image
FROM node:20.15.0-alpine

# Set the working directory to /app
WORKDIR /frontend

# Copy the code
COPY . .

# Expose the port for the development server
EXPOSE 5173

# Install dependencies
RUN npm install

# Run the development server when the container starts
CMD ["npm", "run", "build"]
#set the build stage to build and compile the frontend
FROM node:20.15.0-alpine as build-stage

# Set the working directory to /frontend 
WORKDIR /frontend

#copy the package.json files
COPY package*.json /frontend/

# Install dependencies
RUN npm install

# Copy the rest of the frontend code
COPY . ./frontend/

# Expose the port for the server
EXPOSE 5173

# Run the server when the container starts
RUN npm run build

# Set the next stage to have only the compiled app, ready for production with Nginx
FROM nginx:stable-alpine

COPY --from=build-stage /frontend/dist/ /usr/share/nginx/html

COPY ./nginx.conf /etc/nginx/conf.d/default.conf
COPY ./nginx-backend-not-found.conf /etc/nginx/extra-conf.d/backend-not-found.conf
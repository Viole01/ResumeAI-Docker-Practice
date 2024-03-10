# Build Stage

FROM node:20 AS build

WORKDIR /app

COPY . .

# Install all dependencies
RUN npm install --force
RUN npm i -g @angular/cli
RUN npm install -g angular-http-server

# Create a dist folder
RUN npm run build

# Deployment Stage

FROM nginx:alpine

COPY --from=build /app/dist/resumebuilder /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]

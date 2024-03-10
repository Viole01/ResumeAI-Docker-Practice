FROM node:20

WORKDIR /app

COPY . .

# Install dependencies
RUN npm install --force
RUN npm install -g typescript

# Build the dist folder to upload
RUN tsc --build
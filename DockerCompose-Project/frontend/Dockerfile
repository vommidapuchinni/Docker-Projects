# Use a Node.js LTS image with build tools
FROM node:14 as build

# Set working directory inside the container
WORKDIR /usr/src/app

# Copy package.json and package-lock.json (if exists)
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy rest of the application code
COPY . .

# Build the React app
RUN npm run build

# Use lightweight Node.js image for serving built React app
FROM node:14-alpine

# Set working directory inside the container
WORKDIR /usr/src/app

# Copy build output from previous stage
COPY --from=build /usr/src/app/build ./build

# Expose the port that your app runs on
EXPOSE 3000

# Command to run the app
CMD ["npx", "serve", "-s", "build"]

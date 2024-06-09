# Use a Node.js LTS image
FROM node:14

# Set working directory inside the container
WORKDIR /usr/src/app

# Copy package.json and package-lock.json (if exists)
COPY package*.json ./

# Install dependencies
RUN npm install --production

# Copy rest of the application code
COPY . .

# Expose the port that your app runs on
EXPOSE 5000

# Command to run the app
CMD ["npm", "start"]

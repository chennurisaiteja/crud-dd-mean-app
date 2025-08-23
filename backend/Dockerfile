# Use Node.js LTS
FROM node:18

# Set working directory
WORKDIR /app

# Copy package.json and install dependencies
COPY package*.json ./
RUN npm install

# Copy rest of the backend code
COPY . .

# Expose backend port
EXPOSE 8080

# Start backend
CMD ["node", "server.js"]


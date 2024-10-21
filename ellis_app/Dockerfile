# Stage 1: Build the application
FROM node:18-alpine AS builder

WORKDIR /app

# Copy package.json and package-lock.json to install dependencies
COPY package*.json ./

# Install only dependencies
RUN npm install --only=production

# Copy the rest of the application
COPY . .

# Build the Next.js application
RUN npm run build

# Stage 2: Production container
FROM node:18-alpine

WORKDIR /app

# Copy only the built application from the builder stage
COPY --from=builder /app ./

# Expose the port
EXPOSE 3000

# Start the application
CMD ["npm", "start"]

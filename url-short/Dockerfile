FROM node:18-alpine

WORKDIR /app

# Copy package files
COPY package*.json ./

# Install dependencies
RUN npm ci

# Copy project
COPY . .

# Build React app
RUN npm run build

# Use lightweight server for production
RUN npm install -g serve

EXPOSE 5173

# Serve built app
CMD ["serve", "-s", "dist", "-l", "5173"]

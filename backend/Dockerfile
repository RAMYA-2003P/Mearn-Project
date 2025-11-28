# backend/Dockerfile
FROM node:20-alpine

WORKDIR /usr/src/app

# Install dependencies (use package-lock.json for deterministic install)
COPY package*.json ./
RUN npm ci --production

# Copy source files
COPY . .

ENV NODE_ENV=production
EXPOSE 5000

# If your app's entry is server.js or app.js, adjust:
CMD ["node", "server.js"]

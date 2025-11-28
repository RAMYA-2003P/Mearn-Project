# frontend/Dockerfile
# Build stage
FROM node:20-alpine AS build
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
# angular build (replace project name if needed)
RUN npm run build -- --configuration=production

# Serve stage
FROM nginx:alpine
# Replace dist/<project-name> with your actual dist output folder
COPY --from=build /app/dist/<angular-dist-folder> /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]

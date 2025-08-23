# Stage 1: Build Angular app
FROM node:18 AS build

WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build --prod

# Stage 2: Serve with Nginx
FROM nginx:alpine

# Copy built Angular files to Nginx web root
COPY --from=build /app/dist/angular-15-crud /usr/share/nginx/html

# Copy custom Nginx config (optional)
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]


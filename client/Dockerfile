# Stage 1: Build the React app
FROM node:16-alpine AS build

WORKDIR /app

COPY package.json ./
COPY package-lock.json ./

RUN npm install

COPY . .

RUN npm run build

# Stage 2: Serve the React app with Nginx
FROM nginx:1.23-alpine

COPY --from=build /app/build /usr/share/nginx/html

COPY nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]




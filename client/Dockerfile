FROM node:16-alpine AS build

WORKDIR /app

COPY package.json ./
COPY package-lock.json ./ 

RUN npm install

COPY . .

RUN npm run build

EXPOSE 3000

CMD [ "npm", "start" ]




# FROM nginx:1.23-alpine

# COPY --from=build /app/build /usr/share/nginx/html

# EXPOSE 80

# CMD ["nginx", "-g", "daemon off;"]



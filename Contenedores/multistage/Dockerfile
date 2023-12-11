# Stage 1: Build the Node.js application
FROM node:14
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
#RUN npm run build
# Stage 2: Build the Nginx reverse proxy
FROM nginx:latest
COPY nginx.conf /etc/nginx/conf.d/default.conf
RUN rm /etc/nginx/conf.d/default.conf
COPY nginx.conf /etc/nginx/conf.d/
EXPOSE 80
# Stage 3: Combine the Node.js application and Nginx reverse proxy
FROM node:14
COPY --from=0 /app /app
COPY --from=1 /etc/nginx/conf.d/ /etc/nginx/conf.d/
EXPOSE 80
CMD ["npm", "run", "start"]
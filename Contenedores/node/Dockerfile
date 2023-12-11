FROM node:14

WORKDIR /app

COPY . .

RUN npm install

RUN chmod +x holamundo.js

ENTRYPOINT ["node", "holamundo.js"]
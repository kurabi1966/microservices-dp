FROM node:alpine
WORKDIR /app
COPY package.json ./
RUN npm install
RUN npm instal -g nodemon
COPY ./ ./
CMD ["npm", "start"]
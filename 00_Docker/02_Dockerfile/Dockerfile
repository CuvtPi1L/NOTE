FROM node:19-alpine
# Image env

COPY package.json /app/
COPY code /app/
#/app/ additional slash alow docker create dir if doesn't exist
#you need package to download

WORKDIR /app
#sets defult dir

RUN npm install
# excusting npm install

CMD ["node","server.js"]


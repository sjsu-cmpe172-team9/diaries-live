create dockerfile

FROM node:latest
WORKDIR /urs/src/app
COPY package*.json ./
RUN npm install
RUN npm install --save-dev cross-env
COPY . .
EXPOSE 3000
CMD ["npm","start"]

docker build -t name .

docker run -p 3000:3000 name
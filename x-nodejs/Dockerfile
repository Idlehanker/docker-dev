FROM node:7-alpine
RUN mkdir -p /src/app
WORKDIR /src/app
ONBUILD COPY package.json /src/app/package.json
ONBUILD RUN npm install
ONBUILD COPY . /src/app
ONBUILD EXPOSE 3000
CMD ["npm","start"]

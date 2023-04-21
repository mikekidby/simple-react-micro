FROM node:alpine
 
# Add the following lines
ENV CI=true
ENV WDS_SOCKET_PORT=0
#needed for scss
RUN apk add --no-cache python3 make g++
 
WORKDIR /app
COPY package.json ./
RUN npm install -g sass
RUN npm install
COPY ./ ./
RUN sass ./src/scss/:./src/css/ --style compressed --no-source-map

CMD ["npm", "start"]
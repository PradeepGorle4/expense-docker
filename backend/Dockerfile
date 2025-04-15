# FROM node:20
FROM node:20-alpine3.21
WORKDIR /opt/backend
COPY /code/package.json .
COPY /code/*.js .
RUN npm install
ENV DB_HOST="mysql"
# ENV DB_HOST="localhost" 
#  localhost since we are using host network for docker containers, not the bridge n/w
CMD ["node", "index.js"]

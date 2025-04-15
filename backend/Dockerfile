# FROM node:20
FROM node:20-alpine3.21
RUN addgroup -S expense && adduser -S expense -G expense 
# The above is the cmd for creating user and group in alpine
RUN mkdir /opt/backend
RUN chown -R expense:expense /opt/backend
WORKDIR /opt/backend
COPY /code/package.json .
COPY /code/*.js .
RUN npm install
ENV DB_HOST="mysql"
# ENV DB_HOST="localhost" 
#  localhost since we are using host network for docker containers, not the bridge n/w
USER expense
CMD ["node", "index.js"]

# FROM node:20
FROM node:20-alpine3.21
# The below is the cmd for creating user and group in alpine
RUN addgroup -S expense && adduser -S expense -G expense && \
    mkdir /opt/backend && \
    chown -R expense:expense /opt/backend
WORKDIR /opt/backend
ENV DB_HOST="mysql"
# ENV DB_HOST="localhost" 
#  localhost since we are using host network for docker containers, not the bridge n/w
USER expense
COPY /code/package.json .
COPY /code/*.js ./
RUN npm install
CMD ["node", "index.js"]

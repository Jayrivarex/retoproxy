FROM node:alpine3.10


RUN apk update && apk upgrade && \
    apk add --no-cache bash git openssh


WORKDIR /usr/src/app


RUN git clone https://github.com/Jayrivarex/retoproxy.git


WORKDIR /usr/src/app/retoproxy


RUN npm install --save
RUN npm install mysql

HEALTHCHECK --interval=12s --timeout=12s --start-period=30s \  
    CMD node healthcheck.js


EXPOSE 4000


CMD [ "npm", "start" ]

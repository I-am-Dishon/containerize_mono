# your code goes here ...
FROM node:16.14.0-alpine
# Create app directory
RUN addgroup -S -g 9999  mono  && adduser -S mono -u 9999 -G mono 
WORKDIR /usr/src/app
# Install app dependencies

COPY src/package.json ./
RUN npm install
# Bundle app source
COPY src/index.js ./
COPY --chown=mono:mono . .
USER mono:mono

CMD [ "npm", "run", "main" ]
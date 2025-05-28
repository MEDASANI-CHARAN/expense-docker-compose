FROM node:24.1.0-alpine3.20
EXPOSE 8080
RUN addgroup -S expense && adduser -S expense -G expense
RUN mkdir /opt/server
WORKDIR /opt/server
RUN chown expense:expense -R /opt/server
ENV DB_HOST=mysql
# RUN addgroup -S expense && adduser -S expense -G expense \
#     && mkdir /opt/server \
#     && chown expense:expense -R /opt/server
COPY package.json .
COPY *.js ./
RUN npm install
# USER expense
CMD ["node", "index.js"]
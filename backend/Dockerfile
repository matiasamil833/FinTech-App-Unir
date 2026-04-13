FROM node:25-alpine
WORKDIR /app
EXPOSE 3001
RUN addgroup -S nodegroup && adduser -S nodeuser -G nodegroup
COPY package*.json .
RUN npm install --omit=dev
COPY server.js .
RUN chown -R nodeuser:nodegroup /app
USER nodeuser
ENTRYPOINT [ "node", "server.js" ]
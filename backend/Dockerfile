FROM node:25-alpine
WORKDIR /app
ENV PORT=3001
EXPOSE ${PORT}
COPY package*.json .
RUN npm install --omit=dev
COPY server.js .
ENTRYPOINT [ "node", "server.js" ]
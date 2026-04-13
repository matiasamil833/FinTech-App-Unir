# Stage 1: Build the React app
FROM node:25-alpine AS build
ARG NODE_ENV=production
ENV REACT_APP_API_URL=http://localhost:3001
WORKDIR /app
COPY package*.json .
RUN npm install --omit=dev
COPY public ./public
COPY src ./src
RUN npm run build

# Stage 2: Publish into nginx
FROM nginx:stable-alpine
COPY --from=build /app/build /usr/share/nginx/html

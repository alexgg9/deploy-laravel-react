# Build Stage
FROM node:alpine AS build
RUN apk add --no-cache git
RUN git clone https://github.com/alexgg9/front-gestion-solicitudes.git
#RUN npm install -g vite
WORKDIR /front-gestion-solicitudes
#COPY vite-project/package*.json ./
RUN npm install react-hot-toast
RUN npm install
#COPY vite-project .
RUN npm run build
 
# Production Stage
FROM nginx:stable-alpine AS production
COPY --from=build /front-gestion-solicitudes/dist /usr/share/nginx/html

#Build
#FROM node:alpine as build_stage
FROM tiangolo/node-frontend:10 as build_stage
WORKDIR /app
COPY package*.json .
RUN npm config set registry http://registry.npmjs.org/ && \
  npm config set strict-ssl false 
RUN npm install
COPY . .
#CMD ["npm", "start"]
RUN npm run build

FROM nginx:stable-alpine as prod_stage
COPY --from=build_stage /app/build/ /usr/share/nginx/html
# Copy the default nginx.conf provided by tiangolo/node-frontend
COPY --from=build_stage /nginx.conf /etc/nginx/conf.d/default.conf
CMD ["nginx", "-g", "daemon off;"]
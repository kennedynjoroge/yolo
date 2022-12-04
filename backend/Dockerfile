FROM node:8 as build
WORKDIR /app
COPY package.json .
RUN npm config set registry http://registry.npmjs.org/ && \
  npm config set strict-ssl false 
RUN npm install
COPY . .

FROM node:8-alpine
COPY --from=build /app /
EXPOSE 3001
CMD ["node", "server.js"]
#CMD ["npm", "start"]
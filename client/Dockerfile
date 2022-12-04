FROM node:alpine
WORKDIR /app
COPY package.json ./
COPY ./ ./
RUN npm config set registry http://registry.npmjs.org/ && \
  npm config set strict-ssl false 
RUN npm install
CMD ["npm", "start"]
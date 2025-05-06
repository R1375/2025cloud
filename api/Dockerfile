FROM node:14-alpine
WORKDIR /app
COPY ./api/package.json ./
COPY ./api/app.js ./
RUN npm install
EXPOSE 3000
CMD ["node", "app.js"]

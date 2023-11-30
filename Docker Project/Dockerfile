#Build phase
FROM node:18-alpine as buillder
WORKDIR /usr/app
COPY ./package.json ./
RUN npm install
COPY ./ ./
RUN npm run Build

#Run phase
FROM node:18-alpine
WORKDIR /usr/app
COPY ./package.json ./
COPY --from=builder /usr/app/dist /usr/app
CMD ["node","server.js"]
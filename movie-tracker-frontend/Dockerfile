# frontend/Dockerfile
FROM node:23.7.0 AS builder

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .
RUN npm run build

FROM node:23.7.0

WORKDIR /app

COPY --from=builder /app ./
EXPOSE 3000
CMD ["npm", "start"]

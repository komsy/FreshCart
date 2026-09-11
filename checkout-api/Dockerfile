FROM node:20-alpine

WORKDIR /app

# Upgrade system packages to pull patched versions of libcrypto3/libssl3
RUN apk update && apk upgrade --no-cache

COPY package*.json ./
RUN npm ci --only=production

COPY . .

EXPOSE 3000

CMD ["npm", "start"]
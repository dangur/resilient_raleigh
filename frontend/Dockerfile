FROM node:20-alpine

WORKDIR /app

COPY package.json package-lock.json ./
RUN npm ci

COPY . .

# Next can inline process.env.API_URL at build time. The route fallback is
# localhost:8000, which inside this container is the website itself.
ENV API_URL=http://api:8000
RUN npm run build

EXPOSE 3000

CMD ["npx", "next", "start", "-H", "0.0.0.0", "-p", "3000"]

FROM node:22-alpine

WORKDIR /app
ENV NODE_ENV=production

COPY package.json package-lock.json ./
RUN npm ci --omit=dev --no-audit --no-fund && npm cache clean --force

COPY src/ ./src/
COPY db/init.sql ./db/init.sql

USER node
EXPOSE 3000
CMD ["node", "src/server.js"]

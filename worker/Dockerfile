FROM node:22-alpine

WORKDIR /app

# 1. Dépendances
COPY --chown=node:node package*.json ./
RUN npm ci --omit=dev

# 2. Code applicatif du worker
COPY --chown=node:node . .

# 3. Sécurité : exécution sans privilèges root
USER node

CMD ["node", "worker.js"]



FROM node:22-alpine

WORKDIR /app

<<<<<<< HEAD
# 1. Dépendances
COPY --chown=node:node package*.json ./
RUN npm ci --omit=dev

# 2. Code applicatif du worker
COPY --chown=node:node . .

# 3. Sécurité : exécution sans privilèges root
USER node

CMD ["node", "worker.js"]
=======
COPY --chown=node:node package*.json ./

RUN npm ci --omit=dev

COPY --chown=node:node . .

USER node

CMD ["npm", "start"]
>>>>>>> a83ba591718a38db347deb3bfe1dfb4f763e5c34

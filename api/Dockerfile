<<<<<<< HEAD
ARG BASE=node:22-alpine

FROM ${BASE}

WORKDIR /app

# 1. Dépendances : couche reconstruite uniquement si package*.json change
COPY  --chown=node:node package*.json ./
RUN npm ci --omit=dev

# 2. Code applicatif : change à chaque commit, placé en dernier
COPY --chown=node:node . . 

# 3. Exécution sans privilèges
USER node

EXPOSE 3000
=======
# Image de base : Node.js version 22, légère (alpine)
#FROM node:22-alpine
ARG BASE=node:22-alpine
FROM ${BASE}
# Dossier de travail dans le conteneur
WORKDIR /app

# On copie d'abord juste les fichiers de dépendances (les librairies dont le code a besoin pour fonctionner)
COPY --chown=node:node package*.json ./

# On installe les dépendances
RUN npm ci --omit=dev

# On copie tout le reste du code
COPY --chown=node:node . .

# On utilise un utilisateur normal, pas root (sécurité)
USER node

# Le port utilisé par l'API
EXPOSE 3000

# La commande pour démarrer l'API
>>>>>>> a83ba591718a38db347deb3bfe1dfb4f763e5c34
CMD ["node", "server.js"]
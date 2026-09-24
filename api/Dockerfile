# Image de base : Node.js version 22, légère (alpine)
#FROM node:22-alpine

# Définit l'image de base par défaut.
# Cette valeur peut être modifiée avec --build-arg lors du build.
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
CMD ["node", "server.js"]
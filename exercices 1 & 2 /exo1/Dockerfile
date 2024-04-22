# Utiliser l'image officielle Node.js avec Alpine 6.x
FROM node:6-alpine

# Installer Tini
RUN apk add --no-cache tini

# Créer le répertoire pour les fichiers d'application
WORKDIR /usr/src/app

# Copier le fichier package.json dans le conteneur
COPY package.json .

# Installer les dépendances et nettoyer le cache npm
RUN npm install && npm cache clean --force

# Copier tous les fichiers du répertoire actuel dans l'image
COPY . .

# Démarrer le conteneur avec Tini et Node.js
CMD [ "/sbin/tini", "--", "node", "./bin/www" ]

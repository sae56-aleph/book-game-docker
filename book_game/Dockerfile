FROM nginx:1.25-alpine
MAINTAINER "Enzo MAROS <enzo.maros@etudiant.univ-rennes1.fr>"

WORKDIR /app
RUN apk add --no-cache git nodejs npm

# Initialisation du projet
ADD "https://www.random.org/cgi-bin/randbyte?nbytes=10&format=h" skipcache 
RUN git clone https://github.com/sae56-aleph/book-game

WORKDIR /app/book-game
RUN npm install
COPY .env .env

# Construction de l'application
RUN npm run build
RUN cp -r dist/* /usr/share/nginx/html

# Nettoyage
WORKDIR /usr/share/nginx/html
RUN rm -rf /app
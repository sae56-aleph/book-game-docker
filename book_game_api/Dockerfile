FROM node:21-alpine3.18
MAINTAINER "Enzo MAROS <enzo.maros@etudiant.univ-rennes1.fr>"

WORKDIR /app
RUN apk add --no-cache git bash

# skip cache
ADD "https://www.random.org/cgi-bin/randbyte?nbytes=10&format=h" skipcache 
RUN git clone https://github.com/sae56-aleph/book-game-api

WORKDIR /app/book-game-api
RUN npm install
COPY .env .env

RUN mkdir /app/book-game-api/in /app/book-game-api/out

CMD /bin/sh ./start.sh

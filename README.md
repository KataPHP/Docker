Kata Docker
===========

Créer un fichier **docker-compose.yml** pour notre projet.

## Description

Notre application va être composer de 3 services :
- une base NoSQL **MongoDB**
- une application de visualisation **Mongo Express**
- un serveur **NodeJS**

## Instructions

1) Ajouter un service **db** 
- Image: [Mongo](https://hub.docker.com/_/mongo/)
- Port exposé: 27018
- Volume: aucun
- Variable environnement: aucune

2) Ajouter un Service **dbv**
- Image: [Mongo-express](https://hub.docker.com/_/mongo-express/)
- Port exposé: 8081
- Variable environnement: **ME_CONFIG_MONGODB_SERVER** et **ME_CONFIG_MONGODB_PORT**
- Volume: aucun

3) Ajouter un service **app**
- Image: [node:8.6](https://hub.docker.com/_/node/)
- Port exposé: 3000
- Volume: **répertoire courant** vers **/app**
- Variable environnement: **NODE_ENV**

4) Ajouter un fichier **.dockerignore** :
- node_modules

5) Vérifier dans le projet qu'il y a bien un fichier **package.json** et que le [script de démarrage](https://docs.npmjs.com/misc/scripts#default-values) est bien configuré. 


## Execution

```bash
$ npm install
$ npm start
```
Aller à l'url [http://localhost:3000](http://localhost:3000)

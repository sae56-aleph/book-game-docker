Pour démarrer l'application :
1. Si besoin, s'assurer que tous les conteneurs sont éteints
   ```
   docker compose down
   ```
2. Créer une clé d'API sur [Limewire](https://limewire.com/u/settings/api-keys)
3. Ajouter la clé dans le fichier `book_game_api/.env`
4. Démarrer les conteneurs
   ```
   docker compose up -d --build
   ```

Au premier démarrage, les différents scripts du conteneur `api` vont initialiser les données de l'application.
Pour suivre l'avancement du démarrage :
```
docker compose logs -f api
```

Le serveur est pleinement démarré quand le message `Server running on port ...` est affiché.
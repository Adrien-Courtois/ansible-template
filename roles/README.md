Dossier contenant les rôles ansible

Pour installer un role il faut
- Créer un fichier requirements.yml
```
# from GitHub, overriding the name and specifying a specific tag
- src: https://github.com/Adrien-Courtois/NOM_REPO
  version: BRANCHE
  name: NOM_DONNER_AU_ROLE
```

- Exécuter la commande
```
ansible-galaxy install -r requirements.yml -p .
```

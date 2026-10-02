# Docker - TP1

Ce TP présente l'utilisation de Docker avec une architecture en 3 services :

- `server` : serveur Apache accessible depuis le navigateur ;
- `backend` : API Spring Boot ;
- `database` : base de données PostgreSQL.

Les services communiquent sur 2 réseaux privés `front-network` et `back-network` pour différencier les groupes `backend`/`database` et `backend`/`server`. Le `server` ne peut ainsi jamais communiquer avec la `database`. 

Seul le serveur Apache est exposé sur le port `80`.

## Lancement

Depuis la racine du projet :

```bash
docker compose up --build -d
```

Accéder au serveur : [http://localhost/](http://localhost/)

Les routes `/api/` sont transmises au backend, par exemple :

```
http://localhost/api/students/
http://localhost/api/departments/
```

## Vérification

```bash
docker compose ps
docker compose logs -f
docker compose exec database pg_isready -U usr -d db
```

Le backend et la base de données ne sont pas directement accessibles depuis la machine hôte. Ils sont joignables uniquement entre conteneurs via `backend:8080` et `database:5432`.

## Arrêt

```bash
docker compose down
```

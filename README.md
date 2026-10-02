# Docker - TP2

[Cliquer ici pour voir le TP1](https://github.com/YoannSeurat/Docker-TP2)

Ce TP présente les Github Actions et le monde du CI/CD.

A chaque push sur les branches `main` et `develop`, on gère : 

- les tests du backend
  - avec `mvn clean verify`

- le build et push des images Docker
  - en checkant si `DOCKERHUB_USERNAME` et `DOCKERHUB_TOKEN` existent dans les secrets du repo
  - en se connectant à DockerHub
  - enfin, pour chaque container on build l'image et on push sur DockerHub
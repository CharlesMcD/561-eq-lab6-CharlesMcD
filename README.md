# Lab6
- Travail individuel
- Compte pour 2 points
- Remettre avant la fin du cours du 21 octobre

## Installation
- Copier tout le contenu du lab 6 dans ce repository (**sans le dossier caché .git**)
- Faire un commit et synchroniser

## Objectif
- Exécuter un conteneur sur TravisCi qui démarre les tests unitaires associés à une app web .net core

## Étapes
### Exécution du conteneur en local
- Le dossier **/src** doit contenir les deux dossiers suivants : 
  - **appweb**: Code source de l'application web
  - **appweb.unittests**: Code des tests unitaires. Pour créer un projet de tests, utiliser **dotnet new -t xunittest**. Remplacer le fichier Tests.cs par [celui-ci](https://gist.github.com/ymazieres/37b7dced66808492d4c2b2cb9ab222cd). 
- Ajouter au fichier project.json du projet **appweb.unittests** la dépendance au projet **webapp**. 
- Tester l'exécution des tests en local. Les tests doivent passer.
- Faire les modifications nécessaires pour qu'une image puisse être créée avec l'instruction **docker build -t webapp:test -f ./docker/Dockerfile  .**
- La commande ** docker run -it --rm -v $PWD/packages:/root/.nuget/packages webapp:test ** doit démarrer les tests unitaires.
- Si tout fonctionne: faire un commit est synchroniser sur GitHub

### Exécution du conteneur sur TravisCI
- À la racine du repo créer le fichier **.travis.yml**. Ce fichier doit contenir les instructions nécessaires afin de : 
  - Pourvoir construire l'image docker contenant l'application web et les tests unitaires. 
  - Exécuter le conteneur.
  - Identifier la branche (master) github à aller chercher.
  - Utiliser une "cache" pour stocker les packages entre les différents "builds" de Travis.
- Configurer et lier un compte pour que TravisCI puisse exécuter le conteneur de tests.  


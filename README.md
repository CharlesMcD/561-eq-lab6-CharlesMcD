# Lab6
- Travail individuel
- Compte pour 2 points
- Remettre avant la fin du cours du 21 octobre

## Installation
- Copier tout le contenu du lab 6 dans ce repository (**sans le dossier caché .git**)
- Faire un commit et synchroniser

## Objectif
- Exécuter un conteneur qui démarre les tests unitaires associés à une app web .net core
- La construction de l'image 

## Consignes
### Execution en local
- Le dossier **/src** doit contenir les deux dossiers suivants : 
  - **appweb**: Code source de l'application web
  - **appweb.unittests**: Code des tests unitaires. Pour créer un projet de tests, utiliser **dotnet new -t xunittest**. Remplacer le fichier Tests.cs par [celui-ci](https://gist.github.com/ymazieres/37b7dced66808492d4c2b2cb9ab222cd). 
- Ajouter au fichier project.json du projet **appweb.unittests** la dépendance au projet **webapp**. 
- Tester l'exécution des tests en local. Les tests doivent passer.
- Faire les modifications nécessaires pour qu'une image puisse être créée avec l'instruction **docker build -t webapp:test -f ./docker/Dockerfile  .**
- La commande ** docker run -it --rm -v $PWD/packages:/root/.nuget/packages webapp:test ** doit démarrer les tests unitaires.

### Execution sur TravisCI
- Créer

# Épreuve recrutement Axopen Java / Spring boot

Cette application est utilisée comme exercice de recrutement pour AXOPEN. Il ne représente en rien le niveau de qualité des développements d'AXOPEN.

## Qu'est ce que je dois faire ?

Dans cet exercice, il vous est demandé dans un premier temps, de relire le code et de le comprendre. 
Par la suite, l'objectif est de nous faire un retour sur la qualité du code ainsi qu'une liste des améliorations que vous pourriez apporter à l'application.

Les types de retour peuvent être liés à différentes thématiques, voici une liste non-exhaustive :
- Structure de l'application
- Syntaxe
- Logique
- Lisibilité
- Performance
- Bonnes pratiques


Une fois ces étapes effectuées, vous pouvez nous envoyer votre rapport sous différents formats : 
- Markdown
- Word
- Fichier texte

## Comment lancer l'application ?

> Note : Il n'est pas primordial de lancer l'application pour effectuer l'analyse de code.

Pour lancer le projet il vous faut une base de données `MySQL` qui tourne sur votre poste.

Une fois que `MySQL` est lancé vous allez devoir créer une base de données qui s'intitule `candidature`.

La dernière étape avant de pouvoir lancer l'API sera de modifier les fichiers de configuration pour que l'API pointe sur votre base de données.

Rendez-vous dans le fichier `./src/main/resources/application.properties`

Vous allez devoir modifier la section du haut du fichier en remplacent les éléments par vos informations. 

```properties
############################
# ---    DATASOURCE    --- #
############################
spring.datasource.url=jdbc:mysql://localhost:3306/DB_NAME
spring.datasource.username=DB_USERNAME
spring.datasource.password=DB_PASSWORD
```

Vous pouvez maintenant lancer l'application, le contenu de la base de données va se créer tout seul.

## Que contient l'application ?

Il s'agit d'une API REST, qui permet les interactions suivantes :
- Récupérer un chantier aléatoire
- Mettre à jour un chantier aléatoire
- Récupérer tous les chantiers de l'année courante
- Récupérer tous les chantiers
- Supprimer un chantier par son ID
- Mettre à jour la description d'un chantier par son ID
- Récupérer les properties de l'application

### Architecture du projet

Le code java qui va permettre à l'API de fonctionner se trouve dans le repertoire : `/src/main/java/fr/axopen/candidature`.

Nous allons détailler rapidement ce qui se trouve dans chaque dossier.

- `bo` contient les objets Java qui représentent la base de données.
- `config` contient toute la configuration.
- `dto` contient les classes Java utilisé lors des transactions avec l'utilisateur de l'API. DTO (Data Transfert Object).
- `mapper` Contient les classes qui permettent le mapping.
- `repository` contient les interfaces qui permettent d'interagir avec la base de données.
- `rest` contient les controllers qui sont les points d'entrés de l'API.
- `service` contient les services de l'application.

Le repertoire suivant va contenir les ressources de l'application : `/src/main/resources`.

- `application.properties` contient les propriétés liées à l'API, les paramètres de connexion à la base de données ...
- `db/migration` contient les scripts de migration qui permettent de construire automatiquement la base de données au lancement de l'API.

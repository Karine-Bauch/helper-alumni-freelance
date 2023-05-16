# FEEDBACK4 Parcours Triple Triad

## Vue d’ensemble

Je vois que tu as eu beaucoup de mal sur ce Parcours.
Tu as cependant réussi à installer la DB et afficher les cartes.

Tu as commencé à travailler sur l’accès à une carte et son affichage. Mais tu n’as pas pu terminer.

La prochaine fois, si tu vois que tu bloques, peut-être peux-tu essayer de passer à l’étape d’après, souvent les exercices ne nécessitent pas que le précédent soit terminé pour être réalisé.
Et il arrive que de revenir ensuite sur un exercice débloque la situation.

Et s'il t'arrive, tu peux nous contacter pour que nous puissions t'aiguiller et essayer de te débloquer.

Par ailleurs, il serait surement intéressant de pouvoir prendre un peu de temps ensemble pour voir ce qui t’a bloqué et comment te permettre d’avancer sur les notions de cette saison.

Je te laisse me contacter.

___

## Détails

### router
- Pour afficher les détails d'une carte, il était nécessaire de créer une route paramétrée, c’est-à-dire une route qui prend un paramètre (ici l’id de la carte) et qui permet d’afficher les détails de la carte correspondante. Cette route se définirait ainsi : `router.get('/card/:id', mainController.card);`

### controllers

- `mainController`: Tu as commencé à créer la méthode pour afficher la carte sélectionnée.
Cependant, afin d’afficher la carte, il faut d’abord récupérer l’id de celle-ci grâce à la route paramétrée (voir la correction `mainController.js` méthode `cardDetails`, et de la méthode `getCard` dans le `dataMapper`) mais aussi les informations de la carte, puis mettre à jour la vue `cardList` pour que le lien renvoie bien sur la carte sélectionnée, et la vue `card.ejs` (que tu as créée mais pas modifiée pour n'afficher qu'une carte) pour afficher les informations de la carte sélectionnée.

___

## Approfondissements

Essaie de reprendre les divers challenges de fin de journée, avec les corrections en support au cas où tu bloques sur quelque chose, mais en essayant de faire sans le plus possible.

Tu peux t’aider des fiches Kourou également, relire, rechercher les notions qui te paraissent floues.

Voici quelques liens pour compléter les docs officielles et les cours que tu as suivis :
- [NodeJS + Express partie 2 : Route Parameters]([https://dev.to/ericlecodeur/nodejs-express-partie-2-route-parameters-3n12](https://dev.to/ericlecodeur/nodejs-express-partie-2-route-parameters-3n12))

- [Comment utiliser EJS pour modéliser votre application de noeuds](https://www.digitalocean.com/community/tutorials/how-to-use-ejs-to-template-your-node-application-fr)

- [An Introduction to Queries in PostgreSQL](https://www.digitalocean.com/community/tutorials/introduction-to-queries-postgresql)
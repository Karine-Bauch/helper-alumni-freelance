# FEEDBACK2 Parcours Triple Triad

## Vue d'ensemble :

Tu as bien avancé et tu es presque allé au bout de ce parcours, il ne manquais vraiment pas grand chose pour terminer (juste la suppression d’une carte du deck)

Bravo pour ton travail.
Je suis sûre qu’en reprenant la correction et en essayant de terminer le Parcours avec les bonus tu vas encore progresser.

Attention à mieux nommer tes méthodes et variables afin de plus facilement relire ton code plus tard ou permettre à un autre dev de lire ton code.
Par exemple, à la place de `addDeck` dans ton `deckcontroller`, tu aurais pu mettre `addCardToDeck` ou `addCard` tout simplement.

Essaie aussi d’aérer un peu plus ton code, pour une meilleure lisibilité.

Malgré quelques petites lacunes, tu as compris l'essentiel, on sent qu'il y a du travail derrière.

C'est bien, continue !

___

## Détails :

### index.js

- Il est préférable de mettre ton `secret` de session dans ton .env (voir correction)

### controllers

- Pense à utiliser les blocs try/catch qui permettent de lever des erreurs de requêtes ou d’accès à la DB. Cela permet, si une erreur de ce type se produit, de renvoyer un message et éventuellement des informations sur l’erreur.
- `deckController` : dans ta méthode `addDeck` , il est préférable de sortir la récupération de l’id du bloc `try/catch` comme tu l’as fait dans l’ajout `addCard` afin de bien laisser au bloc `try/catch` la responsabilité unique de capturer une erreur de requête ou d’accès à la DB.

  L’ordre des `try/catch` et `if` peut être optimisé.
En vérifiant d’abord si la carte est présente dans le deck, tu évites de devoir faire toutes les opérations suivante et renvoie direct sur la page deck (voir correction).

  Toujours lever les exceptions en premier.
  
  Ici donc on vérifie s’il y a un deck dans la session, sinon on l’initialise. Ensuite on vérifie si la carte est dans le deck, puis on vérifie si le deck est plein, puis ensuite on va récupérer la carte en DB pour l’ajouter au deck. (je te laisse voir la correction avec cette explication pour bien voir comment on organise cela)
- `getSearchResults` : dans ton `searchController` aux vues de ta méthode, la renommer en `SearchByElement` serait plus approprié, là c’est bien trop vague, mais tu t’en serais rendu compte au moment de créer les autres méthodes de recherche (par valeur, par nom…).

### dataMapper

- Pense à utiliser les requêtes préparées pour éviter les injections SQL.
Tu peux aller voir plus précisément ici ce dont il s’agit :
[https://www.avg.com/fr/signal/sql-injection](https://www.avg.com/fr/signal/sql-injection)
- `getOneCard` : il n’est pas nécessaire de vérifier le nombre de ligne du résultat. Il vaut mieux gérer cela dans le controller.
En vérifiant si la carte existe avant même de la evnoyer à la vue (voir la correction pour plus de détails).

### views

- `deck.ejs` : Recherche ce petit $ qui traine dans ton fichier 😛
Quand au `card.price` es-tu sûr que cela existe dans les données de chaque carte ?

___

## Approfondissements :

Je t’ai déjà mis un lien pour mieux comprendre ce que sont les injections SQL et donc pour comprendre pourquoi il faut réaliser des requêtes préparées.

Tu peux également aller voir un peu plus loin le try/catch pour mieux comprendre son intérêt et son fonctionnement :

- [try...catch - MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Statements/try...catch)

- [Error handling, "try...catch"](https://javascript.info/try-catch)


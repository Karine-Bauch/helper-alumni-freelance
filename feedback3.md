# FEEDBACK3 Parcours Triple Triad

## Vue d’ensemble :

Tu as su installer la base de données et afficher les cartes.
L’affichage d’une carte n’est pas fonctionnel mais tu es finalement passé aux étapes suivantes (recherche par élément, activation des sessions).

C’est bien de ne pas être resté bloqué et d’avoir essayé d’aller plus loin.

Je vois que tu te donnes du mal même si les notions ne sont pas totalement acquises.
Peut-être pourrais-tu refaire certains challenges de fin de journée pour bien assimiler les notions vues en cockpit ?
Après avoir fait ce Parcours, certainement que tu y verras plus clair et pourras voir ce qui a pêché sur ce dernier.

Je te conseille de reprendre le parcours de zéro, en essayant de faire les exercices par toi-même, avec la correction à côté pour te corriger au fur et à mesure.

Continue à travailler, c’est normal d’avoir des difficultés sur certaines notions.
N’hésite pas à nous demander de l’aide (à moi ou aux formateurs) si tu rencontres des points bloquants.

Bravo pour ta persévérance, continue à travailler, ça va payer.
___
## Détails

### index.js

- Il est préférable de mettre ton `secret` de session dans ton .env (voir correction)
- Pas besoin de mettre ceci
  
    `app.use(mainController.cardPage);
    app.use(mainController.notFound);`
    
    dans `index.js` , c’est dans le router que l’on configure l’accès aux différentes pages. Tu peux revoir la doc d’express : [https://expressjs.com/fr/guide/routing.html](https://expressjs.com/fr/guide/routing.html)
    

### router.js

- Inutile de réimporter la session ici puisque c’est déjà fait et utilisé dans le `index.js`
- ta route /search/element ne peut pas fonctionner ainsi.
Tu peux aller voir du côté de la doc express pour reprendre cette notion.

### views

- `cardList.ejs` : petit problème de lien en dehors de l’image. Regarde au niveau de l’organisation de tes balises, en mettant ton image dans la balise `<a>`, cela aurait résolu le pb.
La vue était fournie, quelles raisons t’ont poussé à la modifier ainsi en rajoutant des balises ?
- `cardDetails.ejs` : Ici on cherche à afficher une carte et ses détails.
Tu fais une boucle pour afficher une seule carte ?
Pas nécessaire de faire cette boucle.
Ensuite, compares ce que tu envoies à ta vue avec ce que tu demandes à ta vue d’afficher : dans `mainController` tu envoies oneCard, mais dans ta vue tu demandes d’afficher les infos de `card` 
globalement, fais bien attention de vérifier ce que tu demandes d’afficher. Pour le visuel par exemple, dans les “visuals” les majuscules sont présentes, alors pourquoi faire un `.toLowerCase()` sur le nom du visuel ? Même question pour l’ajout du `.jpg` 😋

### controllers

- `searchController` : mis à part ta route qui n’est pas fonctionnelle (voir la partie ‘router’). Ici, tu appelles une méthode `cardElement` qui n’existe pas dans ton `dataMapper` . J’imagine que tu voulais utiliser la méthode `getCardByElement` (attention à bien vérifier que tu appelles les bonnes méthodes dans tes controllers).

### dataMapper

- Tu aurais pu, par précaution (et pour prendre la bonne habitude) faire une requête préparées aussi pour ton `getAllCards`
- Ta requête préparée pour `getCard` est fonctionnelle, cependant il est plus lisible de faire ainsi :
    
    ```css
    const query = {
    	text: 'ta requete préparée',
    	values: [tableau de values]
    }
    
    const queryResult = await database.query(query)
    ```
    
- `getCard` : Il n’est pas nécessaire de vérifier le nombre de ligne du résultat. Il vaut mieux gérer cela dans le controller.
En vérifiant si la carte existe avant de chercher avant même de la renvoyer à la vue (voir la correction pour plus de détails).
___

## Approfondissements

Afin de pouvoir mieux comprendre les notions abordées dans cette saison, voici quelques liens complémentaires pour t’aider :


- [Route Parameters in Express](https://masteringjs.io/tutorials/express/route-parameters)

- [Comment utiliser EJS pour modéliser votre application de noeuds](https://www.digitalocean.com/community/tutorials/how-to-use-ejs-to-template-your-node-application-fr)

- [An Introduction to Queries in PostgreSQL](https://www.digitalocean.com/community/tutorials/introduction-to-queries-postgresql)
# FEEDBACK1 Parcours Triple Triad

## Vue d'ensemble :
De manière générale, bravo pour ton travail, tu as réussi à terminer ce Parcours haut la main !
Tu as même pu terminer le Bonus 🙌

Tu choisis plutôt bien les noms de tes variables et fonctions.
Ton organisation est claire et tu as bien séparé tes fichiers.

Tu peux améliorer la lisibilité de ton code en espaçant tes méthodes et en aérant un peu plus ton code par moment (par exemple dans `dataMapper.js`).

Beau travail !
Continue comme ça 🚀
____________________

## Détails :

### index.js :

- il manque le SESSION_SECRET dans le .env.example : penser à mettre à jour ce fichier pour permettre à ceux qui cloneront ton repo et voudront l’utiliser de créer leur .env avec les éléments nécessaires
- dans ta session, il n’est pas nécessaire d’ajouter `cookie: {}` si tu ne spécifies aucune option

### router.js :

- RAS, tu aurais pu utuliser ton midleware d'initialisation de deck dans `ìndex.js` mais ce n'est pas une erreur.

### controllers :

- tu as bien organisé tes controllers (main, card, search). Je préfère d'ailleurs ton organisation à celle de la correction.
- Affichage d’une carte : il est préférable de sortir la récupération de l’id du bloc `try/catch` comme tu l’as fait dans l’ajout `addCard` afin de bien laisser au bloc `try/catch`la responsabilité unique de capture d’erreur de requête ou d’accès à la DB.
- Ajout d’une carte au deck : l’ordre des `try/catch` et `if` peut être optimisé.
En vérifiant d’abord si la carte est présente dans le deck, tu évites de devoir faire toutes les opérations suivante et renvoie direct sur la page deck (voir correction).
Toujours lever les exceptions en premier.
Ici donc on vérifie si la carte est dans le deck, puis on vérifie si le deck est plein, puis ensuite on va récupérer la carte en DB pour l’ajouter au deck.
- Page deck : pas nécessaire d’initiialiser le deck puisqu’il l’est déjà dans ton router ton router.

### dataMapper.js :

- Il est toujours préférable d’utiliser les requêtes préparées pour éviter les injections SQL, même sur le `getAllCards`, au moins tu prends les bonnes habitudes.
- Mieux vaut configurer ta requête ainsi :
    
    ```css
    const query = {
    	text: 'ta requete préparée',
    	values: [tableau de values]
    }
    ```
    
    Comme tu l’as fait pour `searchByElement`.
    C’est plus agréable et facile à comprendre (toujours penser à ses collègues et à soi-même dans plusieurs mois, quand tu repasseras sur ton code)
    
- `searchByElementNull` : pas nécessaire puisque tu gères ce cas dans `searchByElement`
- `searchByValues` : Ta proposition de requête est pas mal 👍 et tu as même classé les résultats par ordre croissant !

____________________
## Approfondissement :

Si tu en as envie, tu peux essayer d'ajouter un peu de style à ton projet, via une librairie comme Bootstrap ou Bulma par exemple.
N'hésite pas à 

Si tu le souhaites, tu pourrais approfondir ton travail en approfondissant le travail sur les sessions.
un peu de ressource :

- [https://medium.com/@alysachan830/cookie-and-session-ii-how-session-works-in-express-session-7e08d102deb8](https://medium.com/@alysachan830/cookie-and-session-ii-how-session-works-in-express-session-7e08d102deb8)

- [https://web.dev/understanding-cookies/](https://web.dev/understanding-cookies/)

Plus d'informaitons également sur les injecitons SQL :
- [https://www.avg.com/fr/signal/sql-injection](https://www.avg.com/fr/signal/sql-injection)

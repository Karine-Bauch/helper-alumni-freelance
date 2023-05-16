# FETCH

Salut apprenant !

Il parait que tu veux en savoir plus sur la méthode fetch !

Voici quelques expolications et examples pour t'aider à comprendre comment ça marche.
Je te donnerai des ressources pour aller plus loin à la fin de ce message.
___

## Qu'est-ce que fetch ?
C'est une méthode utilisée pour effectuer des requêtes HTTP asynchrone en Javascript.
Il s'agit d'envoyer une requête à un serveur et d'attendre une réponse.

## Comment ça marche ?
Exemple de requête GET :
```javascript
fetch('https://api.example.com/data')
  .then(response => response.json())
  .then(data => {
    console.log(data);
  })
  .catch(error => {
    console.error('Une erreur s\'est produite:', error);
  });
```
Dans cet example, on envoie une requête GET à l'adresse `https://api.example.com/data`.
La méthode fetch renvoie une promesse qui est résolue lorsque la réponse est reçue.
Puis on utilise la méthode `then` pour récupérer la réponse et la convertir en JSON avec la méthode `json()`, qui renvoie une promesse avec les données parsées (données de la réponse HTTP converties dans un format utilisable par le code JavaScript).
Et enfin on utilise la méthode `then` pour récupérer les données et les utiliser dans le code (ici les afficher dans la console).

Si une erreur se produit, la méthode catch est appelée et affiche l'erreur dans la console.

Exemple de requête POST :
```javascript
// Données à envoyer au serveur, récupérées d'un formulaire par exemple.
const postData = {
  title: 'Mon nouveau post',
  body: 'Contenu de mon post',
  userId: 1
};

// Fetch POST
fetch('https://api.example.com/posts', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify(postData)
})
  .then(response => response.json())
  .then(data => {
    console.log('Post créé avec succès:', data);
  })
  .catch(error => {
    console.error('Une erreur s\'est produite lors de la création du post:', error);
  });
  ```

**Ici on précise dans le deuxième paramètre de la méthode fetch :**

La methode souhaitée (POST)
Les headers (avec le Content-Type qui indique que le corps de la requête est au format json)
Le body (données converties en chaine JSON) dans le deuxième paramètre de la méthode fetch.
Une fois envoyée, on récupère la réponse (de la même manière que pour la requête GET).

Si tu as des questions complémentaires, n'hésite pas à me contacter en MP.

___
## Ressources
- [Requête, réponse et session HTTP](https://www.pierre-giraud.com/http-reseau-securite-cours/requete-reponse-session/)
- [Fetch API](https://developer.mozilla.org/fr/docs/Web/API/Fetch_API)
- [Appel HTTP avec fetch() - Grafikart](https://youtu.be/z9pcgJX1DdY)
- [AJAX](https://developer.mozilla.org/fr/docs/Web/Guide/AJAX)
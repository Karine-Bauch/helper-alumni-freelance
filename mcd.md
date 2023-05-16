# Retour MCD

D'après ce que je comprends de ton MCD :

Tu vas créer une application web, sur laquelle des utilisateurs (USER) pourront commander des mugs (PRODUCT) et les recevoir (ADDRESS).

Chaque utilisateur pourra :
- créer 0 à plusieurs adresses
- passer 0 à plusieurs commandes
- liker 0 à plusieurs mugs

Chaque commande sera composée de 1 à plusieurs mug(s) (sinon elle n'a pas lieu d'être)

Si c'est bien cela, il y a quelques erreurs dans ton MCD :
- Ton MCD peut être écrit en français, car il s'agit de bien poser les bases des besoins "métiers".
- Tes cardinalités sont inversées.
  
  Regarde dans cet exemple :
  ![Alt text](https://www.base-de-donnees.com/wp-content/webp-express/webp-images/doc-root/wp-content/uploads/2017/01/relation-cif.jpg.webp)
  une ville peut ne pas avoir de structure située sur son territoire (cardinalité minimale 0). Par contre, une structure doit obligatoirement se trouver dans une ville (cardinalité minimale 1).
  ([source](https://www.base-de-donnees.com/cardinalites/#:~:text=Comment%20lire%20les%20cardinalit%C3%A9s%20d,%2Cn%20%C2%BB%20du%20c%C3%B4t%C3%A9%20droit.))

- Je rajouterais un attribut number à l'entité ORDER, car un numéro de facture est obligatoire sur une facture (généralement on le formatte ane y mettant la date, le mois, lannée et un numéro automatique, par exemple : 20230516-001).

- On ne met pas d'id dans un MCD, cependant on peut préciser en soulignant le nom de l'attribut si c'est un discriminant (élément unique permettant d'identifier une entité).

  Ici, dans l'entité USER, on peut considérer l'email comme un discriminant car il est unique à chaque utilisateur.

  Même chose pour l'entité ORDER.

  Par contre, dans l'entité ADDRESS, on va rajouter un address_id car nous n'avons pas de discriminant.

  Même chose pour l'entité ORDER.


- La cardinalité entre ADDRESS et USER est mauvaise.
  Il faudrait mettre 1,N côté USER car une adresse appartient au moins à un utilisateur mais peut appartenir à plusieurs également..
  Et 0,N côté ADDRESS car un utilisateur peut avoir plusieurs adresses mais peut ne pas en avoir tant qu'il ne passe aucune commande.

## Forme

- Utilse des ellipse ou des losange pour tes associations pour éviter de les confondre avec les objets
- Pas d'id dans un MCD
- Souligne les discriminants

## Ressources

Voici quelques liens pour compléter tes connaissances :
- [Wikipedia - Modèle entité-association](https://fr.wikipedia.org/wiki/Mod%C3%A8le_entit%C3%A9-association)
- [MERISE - Modèle conceptuel des données](https://web.maths.unsw.edu.au/~lafaye/CCM/merise/mcd.htm#:~:text=Le%20mod%C3%A8le%20conceptuel%20des%20donn%C3%A9es,l)
- [Cardinalités](https://www.base-de-donnees.com/cardinalites/)


Si tu as des questions après avoir revu ton MCD, n'hésite pas à revenir vers moi.

___

## Temps de réalisation du retour : 45min
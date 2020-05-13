# Traducteur legistique

Traducteur pour comparer deux textes 

# Developpement

Dans le projet traducteur-legistique:
- `yarn`
- `yarn test`, pour verifier que tout marche bien
- `yarn build`


# utilisation

Pour utiliser le traducteur légistique il vous suffit de l'installer dans votre projet à l'aide de :

```
npm install --save @socialgouv/traducteur-legistique
```

Puis pour l'utiliser :

```
arrayResult = difflibCalculation(firstText, secondText);
```

Vous avez ensuite accès à différentes informations pour chaque objets de l'array :

```
item.par : Le paragraphe auquel la modification a été effectué

item.new : Si existant, la partie de la phrase qui a été ajouté

item.old : Si existant, la partie de la phrase qui a été supprimé

item.newPar : Si un paragraphe entier a été ajouté il sera dans cette variable 
```

On a donc plusieurs cas possibles :

```
if (item.new && item.old) {
    // Il y a eu modification dans le texte, item.old a été remplacé par item.new     

} else if (item.new && !item.old) {
    // Il y a eu seulement un ajout dans le texte

} else if (item.old && !item.new) {
    // Il y a eu seulement une suppression dans le texte

} else if (item.newPar) {
    // Un nouveau paragraphe a été ajouté au texte
}
```



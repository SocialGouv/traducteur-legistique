# Traducteur legistique

> Traducteur pour comparer deux textes 

# Utilisation

Pour utiliser le traducteur légistique il vous suffit de l'installer dans votre projet à l'aide de :

```sh
$ yarn add @socialgouv/traducteur-legistique
```

Puis pour l'utiliser :

```js
import { difflibCalculation } from "@socialgouv/traducteur-legistique"

const arrayResult = difflibCalculation(firstText, secondText);
```

Vous avez ensuite accès à différentes informations pour chaque objets de l'array :

```ts
interface Item {
  // Le paragraphe sur lequel la modification a été effectuée
  par: string;
  // Si existant, la partie de la phrase qui a été ajoutée
  new?: string;
  // Si existant, la partie de la phrase qui a été supprimée
  old?: string;
  // Si un paragraphe entier a été ajouté il sera dans cette variable
  newPar?: string;
}
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

# Développement

Dans le projet traducteur-legistique:
- `yarn`
- `yarn test`, pour verifier que tout marche bien
- `yarn build`

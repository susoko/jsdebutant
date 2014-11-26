# Javascript pour les débutants

## 1. Javascript

### Pourquoi le javascript ?

Le javascript est un language à la fois simple d'approche et facile à utiliser pour les débutant mais très puissant et complexe pour les experts. Il fonctionne sur tout les navigateurs modernes ( front-end ) ainsi que coté serveur ( back-end ) avec Node.js.

### Les outils

**Votre navigateur** contient déja tout pour vos premières lignes de javascript, un simple `CMD+MAJ+J` sur MAC ou `CTRL+MAJ+J` sur Windows/Linux ouvre la console sur votre navigateur chrome.
> Ouvrez Chrome, et la console et écrivez `alert('Hello Le Wagon')`.

**jsFiddle** : un éditeur en ligne --> http://jsfiddle.net/

Un editeur de texte comme **Sublime Text** ou **Atom** ( qui est d'ailleur écrit entièrement en javascript ) ou simplement Notepad ou Textedit.

### Les variables

Une variable est un identifiant ( unique ) permetant de stocker une donnée ( texte , nombre ou autre )

Pour créer une variable, il faut utiliser l'operateur `var`
> Dans la console : `var maVariable` ensuite `maVariable`

Dans cet exemple nous venons de créer une variable vide, d'où la réponse `undefined` de la console, nous allons voir comment lui attribuer une donnée ( une assignation )

### Les types

Javascript est un language non typé, ça veut dire que l'on est pas obligé de renseigner à l'avance ce que notre variable va contenir, c'est ce que l'on lui assigne qui va renseigner son type

- `number` : contient un **nombre**
- `string` : contient du **texte**, toujours entourés de simple (`'`) ou double guillements(`"`)
- `boolean` : peut contenir **true** ou **false**, vrai ou faux.

> Dans la console : `typeof(4)` , `typeof('Hello')`, `typeof(true)`

j'ai volontairement omis les autres, on les verra plus tard

### Les opérateurs

##### L'opérateur d'assignation

`=` permet d'assigner une donnée à une variable ( à ne pas confondre avec l'égalité en mathématique )
> Dans la console `maVariable = "Bonjour"`

Il en existe d'autres comme `+=`,`-=`...

##### Les opérateurs arithmétiques

Ce sont simplement les signes mathématiques que l'on connait depuis l'école primaire: **addition, soustraction, multiplication et division**.

- `+` : Addition
- `-` : Soustraction
- `/` : Division
- `*` : Multiplication, ne pas utiliser le `x` qui n'est qu'un simple caractère
- `%` : Modulo, le reste d'une division

> Dans la console : `10+10`,`5*3`,`10/10`,`10-3`,`9%2`

##### Les opérateurs de comparaison

Les opérateurs de comparaison retourne un booléen, donc un vrai ou un faux.

- `==` : égal ( `===` égalité stricte )
- `!=` : non égal
- `>` : supérieur ( `>=` , supérieur ou égal )
- `<` : inférieur ( `<=` , inférieur ou égal )

> Dans la console vous pouvez tester tout les opérateurs avec des valeurs `5>3` , `5 == "5"`

Si vous voulez en savoir plus sur les [Expressions et Opérateurs](https://developer.mozilla.org/fr/docs/Web/JavaScript/Guide/Expressions_et_Op%C3%A9rateurs)

### Les fonctions

Une fonction est un morceau de code écrit dans l'optique de pouvoir être reutilisé

```
  var mafunction = function(name){
    return "Bonjour " + name;
  }
```

### Les conditions

```
var nombre = 10;
if(nombre >= 5){
    console.log('plus grand que 5')
}
else {
    console.log('plus petit que 5')
}
```

### Le DOM

Le DOM = Document Object Model, en plus simple c'est ce qu'il y a sous le capot du navigateur, un emsemble d'information sous forme d'un arbre avec des noeuds qui représentent chaque partie d'une page HTML. C'est la ou sont stockée la taille, la couleur et d'autre information pour chaque balise html d'une page web.

> Ouvrez la console, cliquez sur **"Elements"** , séléctionez une balise html ( par exemple `<body>` ) et ensuite cliquez sur **"Propriétés"** dans le bloc de droite, voila c'est ça le DOM

Le javascript peut interagir avec le DOM de la page pour modifier des informations. Mais il y a un grand MAIS, le DOM est en partie standardisé mais pas completement sur tout les navigateurs ( même parfois entre version ). En plus simple, il faut adapter le code selon le navigateur dans certains cas, ce qui demande une certaine expérience et ralentit le developpement.

## 2. jQuery

### C'est quoi jQuery ?

jQuery est une librairie qui permet de faciliter l'usage du javascript, simplifie et accèlere le developpement, et surtout améliore la compatibilité entre les navigateurs.

La documentation complète de jQuery : [api.jquery.com](http://api.jquery.com/)

### Le selecteur

En javascript pur, selectionner un noeud HTML est une tache pénible et compliquée.

En jQuery, le selecteur utilise la logique des sélécteurs CSS.

> Ouvrez [jsFiddle](http://jsfiddle.net/)
>
> Dans la case "javascript", écrivez `$('.montitre')`
>
> Rien ne se passe ? Normal nous avons séléctionné notre élément mais rien de plus
>
> On ajoute `console.log($('.montitre'))` , on survole l'élément dans la fenetre firebug, et notre élément devient jaune dans la page, c'est bon il est sélectionné !
> Si l'on veut changer la couleur de la page il sufft d'utiliser la methode `css()`sur notre élément.  `$('.montitre').css('color','red')`

[En savoir plus sur les selecteurs dans la doc de jquery](http://api.jquery.com/category/selectors/)

### Les évenements

jQuery facilite l'utilisation des évenements, donc capter les interactions de l'utilisateur avec notre page web.

> Retournons à notre fiddle,avec le selecteur nous allons selectionner le bouton et lui ajouter un événement pour modifier la couleur du titre de la page
```
$('.btn').on('click',function(){
    $('.montitre').css('color','red');
});
```
>un click sur le bouton "go" et la couleur passe au rouge !

[En savoir plus sur les évenements dans la doc de jquery](http://api.jquery.com/category/events/)

### Les effets et les animations

Maintenant que nous pouvons gerer des évenements, nous allons animer l'ouverture et la fermeture d'un bloc dans notre page fiddle.

> Dans jsFiddle : Vous l'avez peut-etre remarqué mais un paragraphe n'est pas affiché dans le resultat de notre page. Nous allons l'afficher lors du click sur le bouton.
```
$('.btn').on('click',function(){
    $('.spoiler').show();
});
```

Et si on le faisait apparaitre en slide ? il suffit d'utiliser la méthode slide `slideDown()`! Et si on veut le refermer ensuite ? On peut alors utiliser `slideToggle()`.

[En savoir plus sur les effets dans la doc de jquery](http://api.jquery.com/category/effects/)

### Les requêtes ajax

##### C'est quoi l'AJAX

Asynchronous JavaScript and XML, derrière cette abréviation barbare se trouve un moyen de charger des données sans devoir rafraichir completement la page.

jQuery dispose d'une fonction `$.ajax`

[En savoir plus sur les effets dans la doc de jquery](http://api.jquery.com/category/effects/)

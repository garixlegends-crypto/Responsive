# Les média-queries


## Définition
Les Media Queries correspondent à des styles CSS conditionnels. 
Elles se basent sur la règle CSS *@media* qui va nous permettre de définir différents styles CSS pour différents types d’appareils media et selon différents
 critères.

Elles permettent de présenter le même contenu HTML de différentes façons en fonction de l’appareil utilisé par les visiteurs pour accéder à un site.

## Bonnes pratiques
Depuis quelques années, la majorité des recherches web se font sur mobile. 

C’est la raison principale qui a amené Google à aujourd’hui indexer la version mobile des sites Internet et non plus leur version bureau.

Pour cette raison, il est considéré comme une bonne pratique aujourd’hui de créer son site en version mobile d’abord puis d’utiliser les Media Queries pour modifier la disposition du code pour les écrans d’ordinateurs ou de tablettes. 

## Important à retenir

- Les media queries sont prévues pour surcharger le code écrit avant.
- L'ordre dans lequel elles sont écrites dans le CSS est donc *très important*.
- Il suffit de réécrire le CSS pour les parties HTML qui doivent s'adapter à la taille de l'écran.
- On ne réécrit jamais tout le CSS de la page dans chaque media query, juste ce qui change.
- En fonction de la maquette à intégrer :
    - Toutes les media queries ne sont pas nécessaires (si les formats ordinateur et très grands écrans sont identiques il suffira d'écrire une seule media
     query).
    - Il est parfois nécessaire de prévoir une taille d'écran spéciale juste pour certains éléments HTML, en plus des media queries 'classiques' qui sont
     globalement les suivantes :
        - mobile : 0 -> 775px
        - tablette : 776px -> 991px
        - ordi : 992px -> 1199px
        - grand écran : 1200px et plus


## Le "Mobile First"

1. Le CSS de base est fait pour les écrans type téléphones mobiles.
2. Ensuite on ajoute des media queries pour élargir progressivement la taille de l'écran :
    - Tablette : @media screen and (min-width: 776px) and (max-width: 991px)
    - Ordinateur : @media screen and (min-width: 992px) and (max-width: 1199px)
    - Grand écran : @media screen and (min-width: 1200px)
    
    
## Du format grand écran au mobile

1. Le CSS de base est fait pour les très grans écrans.
2. Ensuite on ajoute des media queries pour diminuer progressivement la taille de l'écran :
    - Ordinateur : @media screen and (min-width: 992px) and (max-width: 1199px)
    - Tablette : @media screen and (min-width: 776px) and (max-width: 991px)
    - Mobile : @media screen and (max-width: 775px)
    
  
  ## Démo à regarder
  1. index.html
    La structure HTML est toujours la même.
    Selon la taille de l'écran certains éléments sont affichés et d'autres non.
    Les couleurs et tailles de polices évoluent également.
    
  2. style.css
    Il y a 2 fichiers différents. Pour voir le résultat de la page en mobile first commenter comme indiqué : 
    
 ```html
<link rel="stylesheet" href="assets/css/style-mf.css">
<!--<link rel="stylesheet" href="assets/css/style-bf.css">-->
 ```

Pour voir le résultat avec les media queries écrites avec l'autre méthode (du grand écran vers le mobile) :

 ```html
<!--<link rel="stylesheet" href="assets/css/style-mf.css">-->
<link rel="stylesheet" href="assets/css/style-bf.css">
 ```

## TP Agrumes
Regardez la vidéo Agrumes.mov.

Les choix de police, des formes et des couleurs sont libres.

Ce qui est imposé :
    - faire changer l'affichage pour chaque format : mobile, tablette, ordinateur et grand écran,
    - la police du titre augmente avec la taille de l'écran
    - la stucture HTML (donnée ci-dessous).

```html
<body>
    <h1>Citron vert</h1>
    <h1>Citron jaune</h1>
    <h1>Orange</h1>
    <h1>Pamplemousse</h1>

    <section>
        <div></div>
    </section>
</body>
```
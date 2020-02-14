class: cover

.highlight[]
# Intégration
.subtitle[Les bonnes pratiques en CSS : organiser proprement l'association HTML 5 et CSS 3]
.line[]

.image-center[
![CSS HTML](https://pixees.fr/wp-content/uploads/2015/11/david_roche_dr_12-300x300.png)
]

---

class: content
.highlight[]
## Quelques rappels
.line[]

Le langage HTML permet de construire la **structure** d'un template.

Le langage CSS *Cascading Style Sheets* permet de **styliser** ces éléments.

.line[]

.image-center[
![BEFORE AFTER CSS](https://phpbridge.org/frontend/img/css_bundler.png)
]

---


class: content
.highlight[]
## Priorités
.subtitle[Notion de cascade]
.line[]

.col[
Plus le code css est près de la balise HTML, plus il est prioritaire.

1. Directive style
```html
<p style=""></p>
```

2. Balise style
```html
<style>
        /* code */
</style>
```

3. Dans un fichier .css chargé via la balise link dans le head
```html
<head>
        <link rel="stylesheet" href="style.css" />
</head>
```
]

---

class: content
.highlight[]
## Priorités
.subtitle[Notion de cascade]
.line[]

.col[
Plus le code css est près de la balise HTML, plus il est prioritaire.

1. Directive style
```html
<p style=""></p>
```

2. Balise style
```html
<style>
        /* code */
</style>
```

3. Dans un fichier .css chargé via la balise link dans le head
```html
<head>
        <link rel="stylesheet" href="style.css" />
</head>
```
]

.col[
Le code chargé en dernier prend la priorité.

L'id a le niveau de priorité le plus fort, ensuite c'est la classe puis la balise.

```css
p {
    color: red;
}

p {
    color: blue;
}

p.text-muted {
    color: grey;
}

p#id {
    color: black;
}
```
]

---

class: content
.highlight[]
## Sélecteurs simples
.subtitle[Naviguer dans le DOM]
.line[]

.col[
Un élément contenant deux classes
```css
.class1.class2 { }
.class1&.class2 { }
```

Un élément contenu dans un autre
```css
.elem1 .elem2 { }
```

Enfants directs (uniquement) d'un élément
```css
.class1 > .class2 { }
```
]

.col[
Élément selon statut
```css
a:hover { }
input[type=radio]:checked { }
```
]

---

class: content
.highlight[]
## Sélecteurs avancés
.subtitle[Naviguer dans le DOM]
.line[]

Le sélecteur adjacent pour agir sur l'élément suivant
```css
.class1 + .class2 { }
.class1 ~ .class2 { }
```

Éléments n'ayant pas une classe
```css
.class1:not(class2) { }
```

Cibler un élement par son index
```css
li:first-child { }

li:nth-child(3) { }
li:nth-child(3n) { }

li:nth-last-of-type(3n) { }
```

---

class: content
.highlight[]
## Positionnements
.subtitle[Position et flottement]
.line[]

.col[
Il y a 3 types de positionnement :

* relative
* absolute
* fixed
]

.col[
Une balise en **position : absolute** se rapporte au **premier parent** ayant une position : **relative**
Elle se place toujours, par défaut, à 0px en haut et à gauche
.line[]

```css
.parent {
    position: relative;
 }
 
.child {
    position: absolute;
    top: 10px;
    left: 50px;
 }
```

Si aucun parent n'est précisé, la balise en position : absolute se rapportera à la balise *html*
]

---

class: content
.highlight[]
## Tailles
.subtitle[px, rem, vh, % ???]
.line[]

* **px** : Pixel
* **%** : Pourcentage


* **vh** : "Viewport height" hauteur de la fenêtre 1vh = 1% de la hauteur de la fenêtre
* **vw** : "Viewport width" largeur de la fenêtre 1vh = 1% de la hauteur de la fenêtre


* **em** : Taille proportionnelle de la police de caractères de l'élément
* **rem** : "Root em" est la taille de la police de caractères dans l'élément racine du document <html>


.line[]
*Contrairement au em, qui peut être différent pour chaque élément, le rem est constant tout au long du document.*

---

class: content
.highlight[]
## Marges
.subtitle[Intérieures, extérieures]
.line[]

* Margin : marges extérieures

* Padding : marges intérieures


.image-right[
![Computed box](https://tutorial.techaltum.com/images/css-boxmodel.png)
]

---

class: content
.highlight[]
## Niveaux de titres
.line[]

.image-right[
![SEO Titles](https://qph.fs.quoracdn.net/main-qimg-d9389403ab1cc626cf27ed3b966dff38)
]

Les balises de type titre sont là pour déclarer le type d'un élément.

Elles favorisent le référencement naturel.

Organisation :
* 1 seul h1
* 2 ou 3 h2
* n h3
* h4

---

class: content
.highlight[]
## Bonnes pratiques
.line[]

.image-center[
![Thank you](https://media0.giphy.com/media/JaWcEIF1RpsVq/giphy.gif)
]

---

class: content
.highlight[]
## Structure
.subtitle[Respecter la hiérarchie HTML5]
.line[]

.image-right[
![Structure HTML5](http://ftsanjuan.com/projects/html5/images/tags_preview.png)
]


.small[Notamment lors de l'utilisation d'un framework frontend.]

.line[]

Une *div* est un conteneur, **élément de bloc** *display: block;*

Un paragraphe *p* est un **élément de bloc** destiné a du texte *display: block;*

Un *span* est un **conteneur en ligne** *display: inline;*

---

class: content
.highlight[]
## Nommage
.subtitle[Utiliser une convention explicite]
.line[]

.image-right[
![BEM](https://blogeduonix-2f3a.kxcdn.com/wp-content/uploads/2018/08/bem.jpeg)
]

Par exemple, la méthodologie *BEM* :

```css
.block__element--modifier {
    /* code */
}
```

.line[]

**Pourquoi ?**

* Modularité
* Réutilisabilité
* Structure

---

class: content
.highlight[]
## Mauvaises pratiques
.subtitle[]
.line[]

.image-center[
![Please don't](https://media2.giphy.com/media/11ykUODgXjAXZu/giphy.gif?cid=3640f6095c068f0963757359517050a4)
]

---

class: content
.highlight[]
## Mélanger les rôles
.subtitle[Utiliser les balises html pour styliser]
.line[]

Par exemple, pour faire ressortir un élément :
```html
<h2>Mon texte</h2>
```

au lieu de
```html
<strong>Mon texte</strong>
ou
<span class="text-strong">Mon texte</span>
```

.line[]
**Pourquoi ?**

Le HTML est un langage déclaratif qui doit être structuré et cohérent.

Il n'est pas fait pour mettre en forme.

Une structure HTML cohérente est indispensable pour un bon référencement.

---

class: content
.highlight[]
## Nommage
.subtitle[Multiplier les classes css]
.line[]

Par exemple :

```html
<p class="text-blue text-center padding-15">Mon texte</p>
```

parce que ça revient quasiment à mettre le css dans le fichier html :

```html
<p style="color: blue; text-align: center; padding: 15px;">Mon texte</p>
```

.line[]
**Pourquoi ?**

Ce que l'on veut c'est gagner du temps et ne pas chercher partout où faire nos modifiations.

Donc il faut que toute la mise en forme soit située au même endroit : fichiers CSS séparés.

---

class: content
.highlight[]
## Surcharge forcée
.subtitle[Mettre des !important partout]
.line[]

Par exemple :
```css
.link {
    color: black !important;
}
```

au lieu de
```css
.navbar .link {
    color: black;
}
```

.line[]
**Pourquoi ?**

Préciser l'architecture parente du composant permet offre des possibilités de surcharge.

Le mot clé !important doit être utilisé de manière exceptionnelle.

---

class: content
.highlight[]
## Mauvais découpage
.subtitle[Mettre des balises de type bloc dans des balises de type inline]
.line[]

Par exemple :
```html
<span>
    <img src="#"/>
    <div>Mon texte</div>
</span>
```

au lieu de :
```html
<div>
    <img src="#"/>
    <p>Mon texte</p>
</div>
```

.line[]
**Pourquoi ?**

Il faut respecter la hiérarchie du DOM (référencement).

Evite les comportements innatendus en CSS.

---

class: content
.highlight[]
## Conseils
.line[]

.image-center[
![Conseils](https://media0.giphy.com/media/AFTWK5Qo22V2g/giphy.gif)
]

---

class: content
.highlight[]
## Organisation
.subtitle[S'organiser autour d'une maquette]
.line[]

.image-right[
![Structure HTML5](http://ftsanjuan.com/projects/html5/images/tags_preview.png)
]

* Identifier ce qui est commun à tous les écrans

* Découper visuellement chaque écran en blocs / grilles

* Travailler le style de façon modulaire

* Penser *mobile first*

---

class: content
.highlight[]
## Découper le code CSS
.subtitle[Partir du global vers du spécifique]
.line[]

1. Identifier les **principales variables** de la charte graphique (couleurs, polices, tailles)

2. Créer un fichier dédié pour les **éléments récurrents** (formulaires, menus, boutons)

3. Créer un fichier css global pour le **layout** (composants communs) de l'application (variables, header, nav, footer, etc)

4. Créer un fichier dédié par **composant**, qui comporteras ajouts et surcharges de style sur les éléments.

---

class: content
.highlight[]
## Utiliser un Framework
.subtitle[et un langage dynamique avec un task runner]
.line[]

.col[
* Utiliser un framework comme **Bootstrap**, **Materialize** ou encore **Bulma**...

.line[]
.line[]
.line[]
.image-mini[
![Bootstrap](https://getbootstrap.com/docs/4.1/assets/img/bootstrap-stack.png)
]
.image-mini[
![Materialize](https://seeklogo.com/images/M/materialize-logo-0FCAD8A6F8-seeklogo.com.png)
]
.image-mini[
![Bulma](https://bulma.io/images/bulma-logo.png)
]
]

.col[
* Utiliser un langage dynamique comme **SASS** ou **LESS**

* Utiliser un task runner comme **Webpack** pour *minifier* et *uglifier* les sorties

.line[]

.image-mini[
![SASS](https://la-cascade.io/content/images/2015/05/sass-logo.svg)
]
.image-mini[
![LESS](http://lesscss.org/public/img/less_logo.png)
]
.image-mini[
![Webpack](https://i0.wp.com/blog.js-republic.com/wp-content/uploads/2018/02/logo-webpack.png)
]
]
---

class: content
.highlight[]
## Ressources supplémentaires
.subtitle[pour la soif de savoir !]
.line[]

.col[
**FR**

* **La Cascade** [https://la-cascade.io/](https://la-cascade.io/)

* **Alsa créations** [https://www.alsacreations.com/](https://www.alsacreations.com/tuto/liste/2-css.html)

.line[]

.image-mini[
![La Cascade](https://la-cascade.io/content/images/2015/03/optimised.svg)
]
.image-mini[
![Alsa créations](https://pbs.twimg.com/profile_images/507471438584885248/OK8krv99_400x400.png)
]

]

.col[
**EN**

* **CSS-Tricks** [https://css-tricks.com/](https://css-tricks.com/)

.line[]

.line[]

.image-mini[
![CSS-Tricks](https://i0.wp.com/css-tricks.com/wp-content/uploads/2019/06/akqRGyta_400x400.jpg)
]

]

---

class: content

.highlight[]
# Et voilà !
.subtitle[Maintenant vous avez toutes les clés pour travailler o/]
.line[]

.image-center[
![](https://media0.giphy.com/media/L0aWDywDu1ziw/giphy.gif?cid=3640f6095c068f6c626f6a6355328a9e)
]

---
class: cover

.highlight[]
# Merci !
.line[]

.image-center[
![](https://media2.giphy.com/media/Gf3fU0qPtI6uk/giphy.gif?cid=3640f6095bfff1227977333345721c64)
]
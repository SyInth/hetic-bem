# Documentation

## Convention BEM
B -> Block
E -> Element
M -> Modifier

```html
<ul clas="mainlList mainList--xmas">


<li class="mainList__item">

  <a class="mainList__itemLink mainList__itemLink--isActive" href="/home">Home </a>

</li>

<li class="mainList__item">

  <a class="mainList__itemLink" href="/about">About </a>

</li>

<li class="mainList__item">

  <a class="mainList__itemLink" href="/works">Works </a>

</li>


</ul>
```
<!--SCSS-->
```css
.mainList {
  display: flex;
  justify-content: space-between;
  &--xmas {
    background: green;

  }
  &__item {
    list-style none;

  }
  &__itemLink {
        color: red;
        &--isActive {
          color: white;
        }
  }
}

/* Rendu CSS normal: .mainList--xmas {}; .mainList__item{};*/

```
## Pseudo attributs

Les pseudos attributs "before" et "after" p-> de créer des noeuds HTML et CSS. Is sont essentiellement utilisés pour ajouter des ornements, décorations... On peut aussi faire des animations, les positionner par rapport à leur parent (relative/absolute). **Ils doivent obligatoirement avoir un `content` ```**
afin de s'afficher.

```HTML
<section class="cover">
<h1 class="cover__mainTiltle"> Présentation des pseudos-attributs </h1>
</section>
```

```css
.cover {
  background: #FDFDFD;
  padding: 20px;
  &__mainTiltle {
    text-align: center;
    font-size: 24px;
    color: green;
    &:: before,
    &::after {
      content: '';
      width: 50px;
      height: 50px;
      background: green;
      top: 0;
    }
    &::before {
      left: 0;
    }
    &::after {
      right: 0;
    }
  }
}

```

## REM, EM, %, VW Sizing

### %

### EM
Relative à son parent direct.

```CSS
.cover {
  font-size: 100%;
  font-size: 16px;
  &__mainTiltle {

    font-size: .8em;
  }
}
```

### REM

* Le REM est basé sur la taille de la racine (soit la balise <html>) qui, par défaut a une valeur de 16px. Afin d'éviter tout calcul, il est nécessaire de l'écraser en donnant une base de 10px, soit 62,5%.

* Le REM est intéressant à utiliser si les medias queries employées sont en rem également. Cela vous permettra de garder des proportions égales lorsqu'on va redimensionner la page.

* Ses proportions seront également gardées quand l'utilisateur zoomera dans votre page.


```css

html {
  font-size: 62,5%;
}
.mainTitle {
  font-size: 1.6rem;
  width: 32rem;
}

```

### VW(idth)/WH(eight)

* Unités relatives à la taille de votre écran (peu importe la device)
* Attention au VH et à son contenu. 100vh=== 100vh quoi qu'il arrive.
* VW: très utiles pour les interfaces fluides.

## Liens utiles:
* [Caniuse](http://caniuse.com)  : c'est compatible avec navigateur?


#Font-face
Le font-face concerne la typographie du site web. C’est un moyen exercé dans le CSS, qui permet de déclarer une police non-standard dans un site web.

Voici les étapes pour intégrer une police personnalisée dans un site web grâce au code :

* Utiliser une police de caractère type True Type (.ttf) ou OpenType (.otf).

* Aller sur un convertisseur comme fontsquirrel.com qui changera le fichier en plusieurs différents (prenons .svg et .woff en exemple de fichier de typographie). Le convertisseur fournira un ensemble de fichiers : 1 fichier .css (feuille de style), 1 fichier .html et des fichiers de typographie.

* Copier le code de la feuille de style puis le coller dans le .css .

* Créer un dossier typo dans un dossier img aussi créé.

* Copier-coller les fichiers de typographie dans le dossier typo.

* Créer un lien dans le fichier.css avec les fichiers (vérifier l’emplacement des fichiers, dans un dossier etc).


Exemple de code dans le fichier.css avec une police « NewFont » :
```css
@font-face {

	font-family: 'NewFont';
        url('../img/typo/ NewFont') format('woff'),
        url('../img/typo/NewFont') format('svg');

}
```
On pourra ensuite coder ainsi, exemple avec une balise de classe ‘header‘ :

```css
.header {
        font-family : ‘typo’, ‘NewFont’ ;
}

```

#Flexbox grid

* Grille de 12 colonnes

* adaptable sur tous les écrans

* A ajouter: "flexbox.grid.min.css" dans le dossier styles

* Faire un link dans le head du html (comme une feuille de style)

```HTML

<section>
	<div class="container">

		<div class="row">

			<div class="col-xs-3 col-sm-3 col-md-4 col-lg-4">

			</div>

		</div>
	</div>
</section>
```

+ : Voir la doc --> flexboxgrid.com

#Positions en CSS

 * Absolute : position dépend du parent

 * Relative : dépend de l'écran

 * Fixed : comme absolute.  Pour créer un élément flottant qui reste à la même position

 * Sticky : se comporte comme un élément positionné de façon relative jusqu'à ce que son bloc englobant dépasse un seuil donné (par exemple fourni par la valeur de top) . Devient fixed après

#<wbr>

Concordonne avec la propriété CSS white-space

*nowrap (permet le rerour à la ligne)
*normal (peut avoir des coupures entre les mots)


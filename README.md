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
* [Caniuse](http://caniuse.com)  : c'est compatible?

---
title: "Expérimentation avec le mode sombre"
author: "Salomé Gfeller"
date: 2023-01-30T17:15:05+01:00
description: Expérimentation avec le mode sombre.
cover: "/blog-labveiltech/img/mode-sombre.png"
tags: ['experimentation', 'article', 'CSS']
draft: false
---

Je suis déjà tombée sur des sites web qui changent d'apparence en fonction du mode de couleur de mon navigateur (clair ou sombre), mais je me suis toujours demandée comment ça se faisait et si c'était possible de faire directement en CSS.

Voici un exemple avec la page d'accueil de Google :

{{< image src="/blog-labveiltech/img/exemple-google.png" alt="google en mode clair et sombre" position="center" style="border-radius: 8px; border: 1px solid #292A2D;" >}}

J'ai ensuite trouvé [un article](https://css-tricks.com/almanac/properties/c/color-scheme/) sur la propriété `color-scheme` en CSS, qui permet de choisir le style par défaut d'une page web, `light` ou `dark`.

## Premier test

J'ai donc fait quelques tests avec une page HTML simple et le code CSS suivant.

```html
<!DOCTYPE html>
<html>
<head>
	<link rel="stylesheet" href="style.css">
</head>
<body>
	<h1>Title</h1>
	<p>paragraph</p>
	<form>
		<input value="Text input" type="text" /></br>
		<input id="checkbox" type="checkbox">
		<label for="checkbox">Checkbox</label></br>
		<input id="radio" type="radio">
		<label for="radio">Radio</label></br>
		<button>Button</button>
	</form>
</body>
</html>
```

```css
:root {
	color-scheme: light dark;
}
```

Voici le résultat, la même page si mon navigateur est en mode clair (gauche) ou sombre (droite).

{{< image src="/blog-labveiltech/img/test1.png" alt="premier test" position="center" style="border-radius: 8px; border: 1px solid #292A2D;" >}}

Mais en quoi est-ce différent d'utiliser le media query `prefers-color-scheme` ?

## Deuxième test

`prefers-color-scheme` permet de voir quel en mode le navigateur est, on pourrait se dire que le code suivant est équivalent au code précédent, juste plus long.

```css
@media (prefers-color-scheme: light) {
	:root {
		background-color: white;
		color: black;
  }
}

@media (prefers-color-scheme: dark) {
	:root {
    background-color: #121212;
    color: white;
  }
}
```

Cependant, on peut voir des différences avec la version précédente (à droite):

{{< image src="/blog-labveiltech/img/test2.png" alt="deuxième test" position="center" style="border-radius: 8px;" >}}

En effet, les checkbox, boutons et imputs de texte, pas toujours très faciles à modifier en CSS, sont en mode "sombre" si on utilise `color-scheme`, car ce sont les styles par défaut du navigateur.

## Troisième test

La puissance de cette propriété est de l'utiliser avec les media queries.

```css
:root {
  color-scheme: light dark;
}

@media (prefers-color-scheme: light) {
  :root {
    background-color: lavender;
    color: darkgreen;
  }
}

@media (prefers-color-scheme: dark) {
  :root {
    background-color: darkolivegreen;
    color: lightpink;
  }
} 
```

Le code suivant permet de personnaliser le style des deux modes, tout en ayant les styles par défaut des checkbox par exemple.

{{< image src="/blog-labveiltech/img/test3.png" alt="troisième test" position="center" style="border-radius: 8px;" >}}

## Conclusion

Maintenant que de plus en plus d'applications proposent un mode sombre, il pourrait être intéressant de faire de même avec nos sites web, et ces propriétés CSS rendent cette idée facilement réalisable.
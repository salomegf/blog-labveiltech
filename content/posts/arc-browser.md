---
title: "Arc est le navigateur du futur"
author: "Salomé Gfeller"
date: 2023-01-24T15:04:44+01:00
description: Présentation du navigateur Arc
cover: "/img/arc-browser.png"
tags: ['article', 'navigateur']
draft: false
---
"The Verge" a publié [cet article](https://www.theverge.com/23462235/arc-web-browser-review) sur le nouveau navigateur "Arc" et j'ai du le tester par moi-même. Mais surtout quels effets est-ce qu'il a sur le développement web.

## Pourquoi

J'ai choisi cet article car en tant que future développeuse web, le navigateur sera un de mes outils de travail principal. J'ai trouvé l'article très intéressant et il m'a donné envie d'essayer un nouveau navigateur.

## Résumé

L'article décrit le navigateur "Arc" et ce qu'il apporte au web. Arc se veut être un système d'exploitation pour le web, en rendant personnalisable et adaptable aux besoins de chacun·es. Cette citation de l'article explique ce concept assez bien :
> Arc treats the web the way TikTok treats video: not as a fixed thing for you to consume but as a set of endlessly remixable components

Arc met ses onglets sur la gauche, au lieu d'en haut dans les navigateurs "classiques", il propose également des "Spaces" qui permettent d'avoir différents espaces avec chacun leurs onglets et favoris (par exemple un pour les cours, et un perso). L'auteur parle également qu'il y a quelques bugs ainsi que des fonctionnalités manquantes, dus au fait que le navigteur est encore en version bêta.

La partie la plus intéressante pour moi et la programmation web est la concept des "Boosts". Ceux-ci permettent de coder en CSS ou JavaScript des mini-extensions afin de personnaliser n'importe quel site web.

## Nouveautés

J'ai donc voulu tester Arc par moi-même et créer un Boost. 

Voici le site web https://chabloz.eu/horaires/ :

{{< image src="/blog-labveiltech/img/arc-avant.png" alt="site web avant" position="center" style="border-radius: 8px; border: 1px solid #292A2D;" >}}

Après avoir écrit le code CSS suivant et l'avoir rajouté au Boost,

```css
:root {
  --color1: rgb(255, 232, 235);
  --color2: rgb(252, 167, 177);
}

body {
  font-family: Roboto Mono !important;
  font-size: 1em !important;
}

h1 {
  background-color: var(--color1) !important;
}

tr:nth-child(odd) {
  background: var(--color1) !important;
}

button {
  border-radius: 5px;
  border-width: 2px;
  border-color: var(--color2);
}

button.selected {
  background: var(--color1) !important;
}
```

Voici le résultat final :

{{< image src="/blog-labveiltech/img/arc-apres.png" alt="site web après" position="center" style="border-radius: 8px; border: 1px solid #292A2D;" >}}

En étant "low code", ces Boosts permettent aux développeur·euses web, ainsi qu'aux personnes avec seulement quelques connaissances de programmation de s'approprier le web. On peut seulement imaginer ce qui est possible de faire avec un outil pareil, et on peut se demander si le futur du web ressemble à Arc.

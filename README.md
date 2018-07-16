<div style="color: #856404; background-color: #fff3cd; border: solid 1px #ffeeba; padding: .75rem 1.25rem; border-radius: .25rem; font-size: 16px;">
  <p style="margin-bottom: 0;">⚠️ Documentation en cours de traduction ️️⚠️</p>
</div>

# <a href='http://redux.js.org'><img src='https://camo.githubusercontent.com/f28b5bc7822f1b7bb28a96d8d09e7d79169248fc/687474703a2f2f692e696d6775722e636f6d2f4a65567164514d2e706e67' height='60' alt='Redux Logo' aria-label='redux.js.org' /></a>

Redux est un conteneur d'état prévisible pour des applications JavaScript.
(Ne pas confondre avec le framework Wordpress - [Redux Framework](https://reduxframework.com/).)

Il vous aide à écrire des applications qui ont un comportement cohérent, fonctionnant dans différents environnements (client, serveur et natif), et qui sont facilement testables. Cerise sur le gâteau, il offre une merveilleuse expérience de développement, comme [l'édition de code en direct combiné avec une gestion d'erreur étape par étape](https://github.com/gaearon/redux-devtools).

Vous pouvez utiliser Redux conjointement avec [React](https://reactjs.org/), ou avec toute autre bibliothèque de vue.  
Il est minuscule (2kb, en incluant les dépendances).

## Apprendre Redux

Nous avons une variété de ressources disponibles pour vous aider à apprendre Redux, peu importe votre parcours ou votre style d'apprentissage.

### Juste les bases

Si vous débutez sur Redux et que vous voulez comprendre les concepts basiques, voir :

- Le **[tutoriel de base dans la documentation de Redux](https://redux.js.org/basics)**
- La série de vidéos gratuites du créateur de Redux, Dan Abramov **["Getting Started with Redux"](https://egghead.io/series/getting-started-with-redux)** sur Egghead.io
- Les diaporamas du comainteneur de Redux Mark Erikson **["Redux Fundamentals"](http://blog.isquaredsoftware.com/2018/03/presentation-reactathon-redux-fundamentals/)** et **[une liste de suggestion de ressources pour apprendre Redux](http://blog.isquaredsoftware.com/2017/12/blogged-answers-learn-redux/)**
- Si vous apprenez mieux en regardant du code et en le manipulant, jetez un oeil à notre liste d'**[exemple d'applications Redux](https://redux.js.org/introduction/examples)**, disponible en projets séparés dans le dépôt de Redux, et aussi nos exemples en ligne interactifs sur CodeSandbox.
- Les **[tutoriaux de Redux](https://github.com/markerikson/react-redux-links/blob/master/redux-tutorials.md)** dans la section **[React/Redux links list](https://github.com/markerikson/react-redux-links)**.  
Voici une liste de tutoriaux que nous recommandons :
  - Les articles de Dave Ceddia [Que fait Redux ? (et quand devriez-vous l'utiliser ?)](https://daveceddia.com/what-does-redux-do/) et [comment Redux fonctionne : un contre-exemple](https://daveceddia.com/how-does-redux-work/) sont de super introductions aux basics de Redux et comment l'utiliser avec React, comme l'article [React et Redux: une introduction](http://jakesidsmith.com/blog/post/2017-11-18-redux-and-react-an-introduction/).
  - L'article de Valentino Gagliardi [tutoriel sur React Redux pour débutant : Apprenez Redux en 2018](https://www.valentinog.com/blog/react-redux-tutorial-beginners/) est une excellente introduction plus approfondie sur de nombreux aspects sur l'utilisation de Redux.
  - l'article de "CSS Tricks" [Niveau supérieur avec React: Redux](https://css-tricks.com/learning-react-redux/) couvre bien les bases de Redux.
  - Le [DevGuides: Introduction à Redux](http://devguides.io/redux/), un  tutoriel qui couvre de nombreux aspects de Redux, incluant les actions, les reducers, l'utilisation avec React et les middlewares.

### Concepts intermédiaires

Une fois que vous avez compris les bases de comment travailler avec les actions, les *reducers* et la mémoire (le *store*), vous pouvez avoir des questions sur des sujets comme, travailler avec la logique asynchrone et les requêtes AJAX, connecter un framework d'interface utilisateur comme React à votre *store* Redux, et mettre en place une application qui utilise Redux :

- La **[section "Advanced" de la documentation](https://redux.js.org/advanced)** couvre des sujets comme travailler avec la logique asynchrone, le middleware, le système de route.
- La page **["Learning Resources"](https://redux.js.org/introduction/learning-resources)** de la documentation de Redux pointe vers des articles recommandés sur une variété de sujets en relation avec Redux.
- La série en 8 partie de Sophie DeBenedetto **[construire une application CRUD simple avec React + Redux](http://www.thegreatcodeadventure.com/building-a-simple-crud-app-with-react-redux-part-1/)** montre comment mettre en place une application CRUD à partir de zéro.

### Usage dans le monde réel

Passer d'une application TodoMVC à une réelle application en production peut être un grand saut, mais nous avons beaucoup de ressources pour aider :

- La série de vidéos gratuites de Dan Abramov le créateur de Redux **["Building React Applications with Idiomatic Redux"](https://egghead.io/courses/building-react-applications-with-idiomatic-redux)**  s'appuie sur sa première série de vidéos et couvre des sujets tels que le middleware, le routage et la persistance.
- La **[FAQ de Redux](https://redux.js.org/faq)** répond à beaucoup de questions communes à propos de comment utiliser Redux, et la **[section "Recipes" de la documentation](https://redux.js.org/recipes)** a des informations sur le traitement des données dérivées, les tests, la logique de structuration des reducers, et les standards pour l'écriture de reducers.
- **[Les séries de tutoriels "Practical Redux"](http://blog.isquaredsoftware.com/series/practical-redux/)** du co-mainteneur de Redux Mark Erikson démontrent des techniques avancées et intermédiaires réelles pour travailler avec React et Redux (aussi disponible en **[un cours interactif sur Educative.io](https://www.educative.io/collection/5687753853370368/5707702298738688)**).
- La **[liste de liens React/Redux](https://github.com/markerikson/react-redux-links)** a catégorisé des articles sur le travail avec [les reducers et les sélecteurs](https://github.com/markerikson/react-redux-links/blob/master/redux-reducers-selectors.md), [la gestion des effets de bord](https://github.com/markerikson/react-redux-links/blob/master/redux-side-effects.md), [l'architecture Redux et les bonnes pratiques](https://github.com/markerikson/react-redux-links/blob/master/redux-architecture.md), et plus encore.
- Notre communauté a crée des milliers de bibliothèques liées à Redux, de modules complémentaires et d'outils.  
La **[page "Ecosystem" de la documentation](https://redux.js.org/introduction/ecosystem)** liste nos recommandations, et il y a une liste complète disponible dans le **[catalogue de modules complémentaire de Redux](https://github.com/markerikson/redux-ecosystem-links)**.
- Si vous cherchez à apprendre à partir du code d'applications réelles, le catalogue de modules complémentaires a également une liste d'**[exemples spécialement conçus et d'applications réelles](https://github.com/markerikson/redux-ecosystem-links/blob/master/apps-and-examples.md)**.

Enfin, Mark Erikson enseigne via une série d'**[ateliers Redux par Workshop.me](#redux-workshops)**.  
Vérifiez le [calendrier des ateliers](https://workshop.me/?a=mark) pour les dates à venir et les emplacements.


### Aide et discussions

Le **[canal #redux](https://discord.gg/0ZcbPKXt5bZ6au5t)** de **[la comunauté Discord Reactiflux](http://www.reactiflux.com)** est notre ressource officielle pour toutes les questions en relation à l'apprentissage et l'usage de Redux.  
Reactiflux est un endroit idéal pour passer un moment, poser des questions et apprendre - venez nous rejoindre !

## Avant d'aller plus loin

Redux est un outil précieux pour organiser l'état de votre application (le *state*), mais il faut aussi se demander si il convient à votre situation.  
N'utilisez pas Redux juste parce que quelqu'un vous a dit que vous devriez - prenez le temps de comprendre les avantages et les compromis potentiels de son utilisation.

Voici quelques suggestions où il convient d'utiliser Redux :

* Vous avez une quantité raisonnable de données qui varient dans le temps
* Vous avez besoin d'une seule source de vérité pour l'état de votre application
* Vous trouvez que garder tout l'état de votre application dans un composant de haut niveau ne suffit plus

Oui, ces lignes directrices sons subjectives et vagues, mais cela est pour une bonne raison. Le moment où vous devriez intégrer Redux dans votre application est différent pour chaque personne ainsi que pour chaque application.

>**Pour d'autres idées sur comment Redux peut-être utilisé, voir :**<br>
>- **[Vous n'avez pas besoin de Redux](https://medium.com/@dan_abramov/you-might-not-need-redux-be46360cf367)**<br>
>- **[Le Tao de Redux, Partie 1 - Implémentation et intention](http://blog.isquaredsoftware.com/2017/05/idiomatic-redux-tao-of-redux-part-1/)**<br>
>- **[Le Tao de Redux, Partie 2 - Pratique et philosophie](http://blog.isquaredsoftware.com/2017/05/idiomatic-redux-tao-of-redux-part-2/)**
>- **[Redux FAQ](https://redux.js.org/faq)**

## Expérience de développement

Dan Abramov (l'auteur de Redux) à écrit Redux en travaillant sur son discours pour React Europe appelé [“Hot Reloading with Time Travel”](https://www.youtube.com/watch?v=xsSnOQynTHs). Son objectif était de créer une bibliothèque de gestion d'état avec une API minimal mais avec un comportememt totalement prévisible, alors il serait possible d'implémenter de la journalisation, du hot reloading, du suivi d'évolution dans le temps, des applications universelles, de l'enregistrement et de la relecture, sans aucun coût supplémentaire pour le développeur.

## Influences

Redux s'inspire des idées de [Flux](http://facebook.github.io/flux/), mais évite sa complexité en s'inspirant d'[Elm](https://github.com/evancz/elm-architecture-tutorial/).  
Même si vous n'avez pas utilisé Flux ou ELM, Redux a besoin seulement de quelques minutes pour démarrer.

## Installation

Pour installer la dernière version :

```
npm install --save redux
```

Cela suppose que vous utilisiez [npm](https://www.npmjs.com/) comme gestionnaire de dépendances.

Si ce n'est pas le cas, vous pouvez [accéder à ces fichiers avec unpkg](https://unpkg.com/redux/),

La plupart des gens utilisent Redux comme un ensemble de modules [CommonJS](http://webpack.github.io/docs/commonjs.html). Ces modules sont ce que vous obtenez quand vous importez `redux` dans [Webpack](https://webpack.js.org/), [Browserify](http://browserify.org/), ou dans un environnement Node. Si vous aimez vivre en marge et utilisez [Rollup](http://rollupjs.org), nous le supportons aussi.

Si vous n'utilisez pas un gestionnaire de regroupements de modules, ce n'est pas grave. Le paquet npm `redux` inclut les versions de production et de développement [UMD](https://github.com/umdjs/umd) dans le [dossier `dist`](https://unpkg.com/redux/dist/). Elles peuvent être utilisées directement sans un "bundler" et sont donc compatibles avec beaucoup d'outils populaires de chargement de modules JavaScript et d'environnements. Par exemple, vous pouvez utiliser un build UMD comme une [`balise <script>`](https://unpkg.com/redux/dist/redux.js) dans la page, ou [indiquer à Bower de l'installer](https://github.com/reactjs/redux/pull/1181#issuecomment-167361975). Les sources UMD permettent à Redux d'être disponible comme variable globale `window.Redux`.

Le code source de Redux est écrit en ES2015, nous le précompilons en CommonJS et UMD vers de l'ES5, donc il fonctionne dans [tous les navigateurs modernes](http://caniuse.com/#feat=es5). Vous n'avez pas besoin d'utiliser Babel ou un gestionnaire de regroupements de modules pour [commencer avec Redux](https://github.com/reactjs/redux/blob/master/examples/counter-vanilla/index.html).

### Paquets complémentaires

Vraisemblablement, vous aurez aussi besoin [de "React bindings"](https://github.com/reactjs/react-redux) et [des "developer tools"](https://github.com/gaearon/redux-devtools).

```
npm install --save react-redux
npm install --save-dev redux-devtools
```

Notez que contrairement à Redux lui-même, beaucoup de paquets de l'écosystème Redux ne fournissent pas de version UMD, donc nous recommandons d'utiliser un gestionnaire de regroupements de modules de type CommonJS comme [Webpack](https://webpack.js.org/) et [Browserify](http://browserify.org/) pour avoir une expérience de développement plus confortable.

## L'essentiel

L'état entier de votre application est enregistré dans un objet à l'intérieur d'un seul *store*.  
Le seul moyen de changer l'état est d'émettre une *action*, un objet décrivant ce qui est arrivé.  
Pour spécifier comment les actions transforment l'état, vous écrivez des *reducers*.

C'est tout!

```js
import { createStore } from 'redux'

/**
 * Ceci est un reducer, une fonction pure avec (state, action) => state signature.
 * Ça décrit comment une action transforme l'état dans l'état suivant.
 *
 * La forme de l'état dépend de vous : cela peut être une primitive, un tableau,
 * un objet, ou même une structure de données Immutable.js. La seule partie
 * importante est que vous ne devez pas modifier l'état de l'objet, mais
 * retourner un nouvel objet si l'état change.
 *
 * Dans cet exemple, nous utilisons un `switch` et des `strings`, mais vous
 * pouvez utiliser un helper qui suit une convention différente (comme des
 * fonctions de map) si c'est mieux pour votre projet.
 */
function counter(state = 0, action) {
  switch (action.type) {
  case 'INCREMENT':
    return state + 1
  case 'DECREMENT':
    return state - 1
  default:
    return state
  }
}

// Créer un store Redux portant l'état de votre application.
// Son API est { subscribe, dispatch, getState }.
let store = createStore(counter)

// Vous pouvez utiliser subscribe() pour mettre à jour l'interface en réponse au changement d'état.
// Normalement vous devez utiliser une bibliothèque de liaison de vue (ex. React Redux) plutôt que d'utiliser subscribe() directement.
// Toutefois il peut également être utile d'enregistrer l'état local dans le localStorage.
store.subscribe(() =>
  console.log(store.getState())
)

// La seule façon de modifier l'état interne est de dispatcher une action.
// Les actions peuvent être sérialisées, logguées ou enregistrées et rejouées plus tard.
store.dispatch({ type: 'INCREMENT' })
// 1
store.dispatch({ type: 'INCREMENT' })
// 2
store.dispatch({ type: 'DECREMENT' })
// 1
```

Au lieu de changer l'état directement, vous spécifiez le changement que vous voulez voir avec un objet appellé *actions*. Ensuite vous écrivez une fonction spéciale appelée un *reducer* pour déterminer comment chaque action transforme l'état de l'application en entier.

Si vous venez de Flux, il y a une différence importante que vous devez saisir. Redux n'as pas de *Dispatcher* et n'accepte pas plusieurs *stores*. Au lieu de ça, il y a seulement un seul *store* avec une unique fonction reducer. Lorsque votre application grossira, au lieu d'ajouter des *stores*, vous séparerez le reducer principal en petit reducers indépendant opérant sur les différentes parties de l'état applicatif. De la même façon qu'il y a juste un composant principal dans une application React, mais composé de beaucoup de petit composant.

Cette architecture peut sembler exagérée pour une application de compteur, mais la beauté de ce modèle est la manière dont il s'adapte aux applications volumineuses et complexes. Il permet également d'activer des outils de développement très puissants, car il est possible de tracer chaque mutation à l'action qui l'a provoquée. Vous pouvez enregistrer des sessions utilisateur et les reproduire simplement en rejouant chaque action.

## Apprenez Redux de ses autheurs

### Les tutoriaux vidéo de Redux par Dan Abramov

#### Premiers pas avec Redux

**[Commencer avec Redux](https://egghead.io/series/getting-started-with-redux)** est un cours vidéo composé de 30 vidéos narrées par [Dan Abramov](https://twitter.com/dan_abramov), auteur de Redux. Il est pensé pour compléter la partie "Les bases" de la documentation tout en apportant des informations supplémentaires sur l'immutabilité, les tests, les bonnes pratiques pour Redux, et utiliser Redux avec React. **Ce cours est gratuit et le restera toujours.**

>["Très bon cours sur egghead.io par @dan_abramov - au lieu de juste montrer pourquoi vous devez utiliser #redux, il montre aussi comment et pourquoi redux a été créé !"](https://twitter.com/sandrinodm/status/670548531422326785)  
>Sandrino Di Mattia

>["Creusez à travers 'Getting Started with Redux' de @dan_abramov - c'est incroyable combien les concepts sont plus simples avec la vidéo."](https://twitter.com/chrisdhanaraj/status/670328025553219584)  
>Chris Dhanaraj

>["La série de vidéos sur Redux par @dan_abramov sur @eggheadio est spectaculaire !"](https://twitter.com/eddiezane/status/670333133242408960)  
>Eddie Zaneski

>["Venez pour le nom hype. Resetez pour les fondamentaux solide comme de la roche. (Merci, et très bon travail @dan_abramov et @eggheadio!)"](https://twitter.com/danott/status/669909126554607617)  
>Dan

>["Cette série de vidéo sur Redux par @dan_abramov tourne sans cesse dans mon esprit - je dois sérieusement faire du refactoring"](https://twitter.com/gelatindesign/status/669658358643892224)  
>Laurence Roberts

Alors qu'est-ce vous attendez ? 

#### [Regardez la série de vidéos gratuite "Getting Started with Redux"](https://egghead.io/series/getting-started-with-redux)

> Note: Si vous aimez les cours de Dan, pensez à supporter Egghead en [souscrivant à un abonnement](https://egghead.io/pricing). Les abonnées ont accès au code source pour chaque exemple de mes vidéos et des tonnes de leçons avancées sur d'autres sujets, incluant les profondeurs de JavaScript, React, Angular, et plus. Beaucoup d'[instructeurs Egghead](https://egghead.io/instructors) sont aussi des auteurs de bibliothèques libres (open source), donc prendre un abonnement est une bonne manière de les remercier pour le travail qu'ils ont fait.

#### Construisez des applications React avec Redux

Le cours **[construisez des applications React avec Redux](https://egghead.io/courses/building-react-applications-with-idiomatic-redux)** course est la seconde série de vidéos gratuite de Dan Abramov.  
Il reprend là où la première série s'est arrêtée, et couvre des techniques prêtes pour la production pour créer vos applications React et Redux : une gestion avancée du *state*, de middleware, l'intégration de React Router, et d'autres problèmes communs que vous risquez de rencontrer lors de la création d'applications pour vos clients et vos utilisateurs.  
Comme avec la première série, **ce cours sera toujours gratuit**.

#### [Regarder la série de vidéos gratuite "Idiomatic Redux"](https://egghead.io/courses/building-react-applications-with-idiomatic-redux)

### Cours pratique - Redux

**["Practical Redux"](https://www.educative.io/collection/5687753853370368/5707702298738688/)** est un cours interactif payant par le co-mainteneur de Redux [Mark Erikson](https://twitter.com/acemarke).  
Le cours est pensé pour montrer comment appliquer les concepts basiques de Redux pour construire quelque chose de plus grand qu'une application de TodoMVC.  
Il comprend des sujets du monde réel comme :

- Ajouter Redux à un nouveau projet créé avec Create-React-App et configurer le rafraîchissement en temps réel (Hot Module Replacement) pour un développement plus rapide.
- Contrôler votre comportement d'interface utilisateur avec Redux
- Utilisation de la bibliothèque Redux-ORM pour gérer les données relationnelles dans votre *store* Redux
- Construire une vue maître/détail pour afficher et éditer des données
- Écrire une logique de reducer Redux personnalisé pour résoudre des problèmes spécifiques
- Optimisation des performances de Redux-connected pour les champs de formulaire

Et plus encore !  

Le cours est basé sur **[la série de tutoriels gratuits "Pratical Redux"](http://blog.isquaredsoftware.com/series/practical-redux/)** du blog de Mark, mais avec du contenu mis à jour et amélioré.

### Ateliers sur Redux

Le co-mainteneur de Redux [Mark Erikson](https://twitter.com/acemarke) s'est associé avec [Workshop.me](https://workshop.me/) pour enseigner une série d'ateliers sur Redux

Le premier [atelier **Redux Fundamentals** se tiendra à New York du 19 au 20 avril](https://workshop.me/2018-04-react-redux?a=mark) et couvrira :

- L'histoire et le but de Redux
- Les *reducers*, les *actions* et comment travailler avec le *store* de Redux
- Utiliser Redux avec React
- Utiliser et écrire des middlewares Redux
- Travailler avec des appels AJAX et d'autres effets secondaires
- Tester unitairement vos applications Redux
- Structure et développement d'une application Redux dans le monde réel

Les tickets sont toujours disponibles et [peuvent être achetés sur Workshop.me](https://workshop.me/2018-04-react-redux?a=mark).

## Documentation

* [Introduction](https://yasakura.github.io/redux-in-french/docs/introduction/index.html)
* [Les bases](https://yasakura.github.io/redux-in-french/docs/basics/index.html)
* [Perfectionnement](https://yasakura.github.io/redux-in-french/docs/advanced/index.html)
* [Recettes](https://yasakura.github.io/redux-in-french/docs/recipes/index.html)
* [FAQ](https://yasakura.github.io/redux-in-french/docs/FAQ.html) 
* [Dépannage](https://yasakura.github.io/redux-in-french/docs/Troubleshooting.html)
* [Glossaire](https://yasakura.github.io/redux-in-french/docs/Glossary.html)
* [Référence de l'API](https://yasakura.github.io/redux-in-french/docs/api/index.html)

Pour les exportations en PDF, ePub et MOBI pour la lecture hors ligne, vous pouvez consulter les instructions pour les créer ici : [paulkogel/redux-offline-docs](https://github.com/paulkogel/redux-offline-docs).

Pour la documentation hors ligne (en anglais) vous pouvez la voir sur [devdocs](http://devdocs.io/redux/)

## Exemples

Presque tous les exemples ont un CodeSandbox correspondant. C'est une version interactive du code que vous pouvez voir en ligne.

* [**Compteur Vanilla**](https://redux.js.org/introduction/examples#counter-vanilla): [Source](https://github.com/reactjs/redux/tree/master/examples/counter-vanilla)
* [**Compteur**](https://redux.js.org/introduction/examples#counter): [Source](https://github.com/reactjs/redux/tree/master/examples/counter) | [Sandbox](https://codesandbox.io/s/github/reactjs/redux/tree/master/examples/counter)
* [**Todo**](https://redux.js.org/introduction/examples#todos): [Source](https://github.com/reactjs/redux/tree/master/examples/todos) | [Sandbox](https://codesandbox.io/s/github/reactjs/redux/tree/master/examples/todos)
* [**Todos avec annulation**](https://redux.js.org/introduction/examples#todos-with-undo): [Source](https://github.com/reactjs/redux/tree/master/examples/todos-with-undo) | [Sandbox](https://codesandbox.io/s/github/reactjs/redux/tree/master/examples/todos-with-undo)
* [**TodoMVC**](https://redux.js.org/introduction/examples#todomvc): [Source](https://github.com/reactjs/redux/tree/master/examples/todomvc) | [Sandbox](https://codesandbox.io/s/github/reactjs/redux/tree/master/examples/todomvc)
* [**Panier d'achats**](https://redux.js.org/introduction/examples#shopping-cart): [Source](https://github.com/reactjs/redux/tree/master/examples/shopping-cart) | [Sandbox](https://codesandbox.io/s/github/reactjs/redux/tree/master/examples/shopping-cart)
* [**"Tree View"**](https://redux.js.org/introduction/examples#tree-view): [Source](https://github.com/reactjs/redux/tree/master/examples/tree-view) | [Sandbox](https://codesandbox.io/s/github/reactjs/redux/tree/master/examples/tree-view)
* [**Asynchrone**](https://redux.js.org/introduction/examples#async): [Source](https://github.com/reactjs/redux/tree/master/examples/async) | [Sandbox](https://codesandbox.io/s/github/reactjs/redux/tree/master/examples/async)
* [**Universel**](https://redux.js.org/introduction/examples#universal): [Source](https://github.com/reactjs/redux/tree/master/examples/universal)
* [**Monde réel**](https://redux.js.org/introduction/examples#real-world): [Source](https://github.com/reactjs/redux/tree/master/examples/real-world) | [Sandbox](https://codesandbox.io/s/github/reactjs/redux/tree/master/examples/real-world)

Si vous êtes nouveau avec l'écosystème de NPM et avez des problèmes pour récupérer et lancer un projet, ou n'êtes pas sûr de savoir où coller l'essentiel des liens ci-dessus, regarder ["simplest-redux-example"](https://github.com/jackielii/simplest-redux-example) qui utilise Redux avec React et Broserify.

## Témoignages

>[“J'aime ce que vous faites avec Redux”](https://twitter.com/jingc/status/616608251463909376)
>Jing Chen, créateur de Flux

>[“J'ai demandé des commentaires sur Redux dans un groupe de discussion interne JS chez Facebook, et il était reconnu universellement. C'est vraiment un travail remarquable.”](https://twitter.com/fisherwebdev/status/616286955693682688)
>Bill Fisher, auteur de la documentation de Flux

>[“C'est bien que vous ayez inventé un meilleur Flux en ne faisant pas du tout comme Flux.”](https://twitter.com/andrestaltz/status/616271392930201604)
>André Staltz, créateur de Cycle

## Remerciements

* [L'architecture ELM](https://github.com/evancz/elm-architecture-tutorial) pour une excellente introduction à la modélisation de mises à jour d'états avec des reducers;
* [Renverser la base de données](http://www.confluent.io/blog/turning-the-database-inside-out-with-apache-samza/) pour me faire perdre la tête;
* [Développer ClojureScript avec Figwheel](https://www.youtube.com/watch?v=j-kj2qwJa_E) pour me convaincre que la réévaluation devrait "juste fonctionner";
* [Webpack](https://webpack.js.org/concepts/hot-module-replacement/) pour le rechargement des modifications à chaud (Hot Module Replacement);
* [Flummox](https://github.com/acdlite/flummox) pour m'apprendre à approcher Flux sans passe-partout ou singletons;
* [disto](https://github.com/threepointone/disto) pour une preuve de concept de Stores rechargeable à chaud;
* [NuclearJS](https://github.com/optimizely/nuclear-js) pour prouver que cette architecture peut-être performante;
* [Om](https://github.com/omcljs/om) pour populariser l'idée d'un seul état atomique;
* [Cycle](https://github.com/cyclejs/cycle-core) pour montrer comment souvent une fonction est le meilleur outil;
* [React](https://github.com/facebook/react) pour l'innovation pragmatique.

Remerciement spécial à [Jamie Paton](http://jdpaton.github.io) pour le transfert du nom du paquet npm 'redux'.

## Logo

Vous pouvez trouver le logo officiel [sur GitHub](https://github.com/reactjs/redux/tree/master/logo).

## Journal de modifications

Ce projet adhère à ["Semantic Versioning"](http://semver.org/).  
Chaque version, avec les instructions de migration, est documentée sur la page [Releases](https://github.com/reactjs/redux/releases) de Github.

## Mécènes

Le travail sur Redux a été [financé par la communauté](https://www.patreon.com/reactdx).  
Rencontrez certaines des entreprises exceptionnelles qui ont rendu ça possible : 

* [Webflow](https://github.com/webflow)
* [Ximedes](https://www.ximedes.com/)

[Voir la liste complète des clients Redux](PATRONS.md), ainsi que la liste toujours croissante de [personnes et d'entreprises qui utilisent Redux](https://github.com/reactjs/redux/issues/310).

## License

MIT

<div style="color: #856404; background-color: #fff3cd; border: solid 1px #ffeeba; padding: .75rem 1.25rem; border-radius: .25rem; font-size: 16px;">
  <p style="margin-bottom: 0;">⚠️ En cours de traduction ️️⚠️</p>
</div>

# Art antérieur

Redux à un héritage mixte. Il est similaire à certains modèles et technologies, mais est également différent d'eux de manière importante. Nous explorerons certaines des similitudes et des différences ci-dessous.

### Flux

Redux peut-il être considéré comme une implémentation de [Flux](https://facebook.github.io/flux/)?  
[Oui](https://twitter.com/fisherwebdev/status/616278911886884864) et [non](https://twitter.com/andrestaltz/status/616270755605708800).

(Pas d'inquiétude, [les créateurs de Flux](https://twitter.com/jingc/status/616608251463909376) [approuvent ça](https://twitter.com/fisherwebdev/status/616286955693682688), si c'est tout ce que vous vouliez savoir.)

Redux a été inspiré par plusieurs qualités importantes de Flux. Comme Flux, Redux vous prescrit de concentrer votre logique de mise à jour de votre modèle dans une certaine couche de votre application ("*stores*" dans Flux, "*reducers*" dans Redux). Au lieu de laisser le code de l'application muter directement les données, les deux vous disent de décrire chaque mutation comme un objet simple appelé "action".

Contrairement à Flux, **Redux n'a pas le concept de _Dispatcher_**. C'est dû au fait qu'il s'appuie sur des fonctions pures plutôt que sur des émetteurs d'événements (*event emmitters*), et que les fonctions pures sont faciles à composer n'ont pas besoin d'une autre entité pour les gérer. Selon la façon de comment vous voyez Flux, vous pouvez voir cela comme un écart ou un détail d'implémentation. Flux a souvent été [décrit comme `(state, action) => state`](https://speakerdeck.com/jmorrell/jsconf-uy-flux-those-who-forget-the-past-dot-dot-dot-1). En ce sens, Redux est fidèle à l'architecture Flux, mais la rend plus simple grâce aux fonctions pures.

Une autre différence importante avec Flux est que **Redux suppose que vous ne modifiez jamais vos données**. Vous pouvez utiliser de simples objets et des tableaux pour votre *state*, mais les modifier à l'intérieur des *reducers* est fortement déconseillé. Vous devez toujours renvoyer un nouvel objet, ce qui est facile avec [la proposition de syntaxe de décomposition d'objet](../recipes/UsingObjectSpreadOperator.md), ou avec une bibliothèque comme [Immutable](https://facebook.github.io/immutable-js).

Bien qu'il soit techniquement *possible* [d'écrire des *reducers* impurs](https://github.com/reduxjs/redux/issues/328#issuecomment-125035516) qui modifient les données pour des cas de performances, nous vous décourageons activement de faire ça. Les fonctionnalités de développement comme le voyage dans le temps, l'enregistrement/la relecture, où le rechargement à chaud seront interrompus. De plus, il ne semble pas que l'immutabilité pose des problèmes de performance dans la plupart des applications réelles, car, comme le démontre [Om](https://github.com/omcljs/om), même si vous perdez en affectation d'objet, vous gagnez toujours à éviter des re-rendus et re-calculs coûteux, car vous savez exactement ce qui a changé grâce à la pureté du *reducer*.

### Elm

[Elm](http://elm-lang.org/) est un langage de programmation fonctionnel inspiré par Haskell et créé par [Evan Czaplicki](https://twitter.com/czaplic). Il applique [une architecture de "mise à jour de vue de modèle"](https://github.com/evancz/elm-architecture-tutorial/), où la mise à jour a la signature suivante: `(action, state) => state`. Les *updaters* Elm ont le même objectif que les *reducers* dans Redux.

Contrairement à Redux, Elm est un langage, donc il est capable de tirer parti de nombreuses choses comme la pureté forcée, le typage statique, l'immutabilité prête à l'emploi, et la correspondance de modèles (en utilisant l'expression `case`). Même si vous ne prévoyez pas d'utiliser Elm, vous devriez lire sur l'architecture d'Elm, et jouer avec. Il y a un [terrain de jeu de bibliothèque JavaScript de mise en œuvre d'idées similaires](https://github.com/paldepind/noname-functional-frontend-framework). Nous devrions chercher ici l'inspiration sur Redux ! Une des façons d'être plus proche du typage statique d'Elm est [d'utiliser une solution de typage progressive comme Flow](https://github.com/reduxjs/redux/issues/290).

### Immutable

[Immutable](https://facebook.github.io/immutable-js) est une bibliothèque JavaScript implémentant des structures de données persistantes. Elle est performante et à une API JavaScript idiomatique.

Immutable et la plupart des bibliothèques similaires sont orthogonales à Redux. N'hésitez pas à les utiliser ensemble !

**Redux ne se soucie pas *de comment* vous stockez le *state*, il peut s'agir d'un objet simple, un objet Immutable, ou n'importe quoi d'autre**. Vous voudrez probablement un mécanisme de sérialisation pour écrire des applications universelles et charger leur *state* à partir du serveur, mais à part cela, vous pouvez utiliser n'importe quelle bibliothèque de stockage de données *tant qu'elle supporte l'immutabilité*. Par exemple, il n'y a pas de sens y à utiliser Backbone pour le *state* de Redux, car les modèles de Backbone sont mutables.

Notez que, même si votre bibliothèque immuable supporte les pointeurs, vous ne devez pas les utiliser dans une application Redux. L'ensemble de l'arbre de *state* doit être en lecture seule, et vous devez utiliser Redux pour mettre à jour le *state*, et souscrire aux mises à jour. Donc écrire via un pointeur n'a pas de sens pour Redux. **Si votre seul cas d'utilisation des pointeurs est de découpler l'arbre de *state* de l'arborescence le l'interface utilisateur et d'affiner progressivement les pointeurs, vous devriez regarder les sélecteurs.** Les sélecteurs sont des fonctions composables. Voir [reselect](http://github.com/faassen/reselect) pour une implémentation vraiment géniale et concise des sélecteurs composables.

### Baobab

[Baobab](https://github.com/Yomguithereal/baobab) is another popular library implementing immutable API for updating plain JavaScript objects. While you can use it with Redux, there is little benefit in using them together.

Most of the functionality Baobab provides is related to updating the data with cursors, but Redux enforces that the only way to update the data is to dispatch an action. Therefore they solve the same problem differently, and don't complement each other.

Unlike Immutable, Baobab doesn't yet implement any special efficient data structures under the hood, so you don't really win anything from using it together with Redux. It's easier to just use plain objects in this case.

### RxJS

[RxJS](https://github.com/ReactiveX/RxJS) is a superb way to manage the complexity of asynchronous apps. In fact [there is an effort to create a library that models human-computer interaction as interdependent observables](http://cycle.js.org).

Does it make sense to use Redux together with RxJS? Sure! They work great together. For example, it is easy to expose a Redux store as an observable:

```js
function toObservable(store) {
  return {
    subscribe({ next }) {
      const unsubscribe = store.subscribe(() => next(store.getState()))
      next(store.getState())
      return { unsubscribe }
    }
  }
}
```

Similarly, you can compose different asynchronous streams to turn them into actions before feeding them to `store.dispatch()`.

The question is: do you really need Redux if you already use Rx? Maybe not. It's not hard to [re-implement Redux in Rx](https://github.com/jas-chen/rx-redux). Some say it's a two-liner using Rx `.scan()` method. It may very well be!

If you're in doubt, check out the Redux source code (there isn't much going on there), as well as its ecosystem (for example, [the developer tools](https://github.com/reduxjs/redux-devtools)). If you don't care too much about it and want to go with the reactive data flow all the way, you might want to explore something like [Cycle](http://cycle.js.org) instead, or even combine it with Redux. Let us know how it goes!

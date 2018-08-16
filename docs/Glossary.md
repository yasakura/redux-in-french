# Glossaire

C'est un glossaire des termes de base dans Redux, avec leurs signatures de type. Les types sont documentés en utilisant [Flow notation](http://flowtype.org/docs/quick-reference.html).

## State

```js
type State = any
```

*State* (aussi appelé *arbre de state* ou *state tree* en anglais) est un terme générique, mais dans l'API de Redux, il fait référence généralement à la valeur du *state* unique qui est géré par le store et retourné par [`getState()`](api/Store.md#getState). Il représente l'état entier d'une application Redux, qui est souvent un objet profondément imbriqué.

Par convention, le *state* de premier niveau est un objet ou une autre collection de valeur-clé comme une carte, mais techniquement il peut être de n'importe quel type. Cependant, vous devriez faire de votre mieux pour garder le *state* sérialisable. Ne mettez rien à l'intérieur que vous ne pouvez pas facilement transformer en JSON.

## Action

```js
type Action = Object
```

Une *action* est un simple objet qui représente une intention de changer le *state*. Les actions sont la seule façon d'obtenir les données dans le *store*. Toutes les données, qu'il s'agisse d'événements de l'interface utilisateur, les rappels réseau ou d'autres sources telles que les *WebSockets* doivent éventuellement être dispatcher en tant qu'actions.

Les actions doivent avoir un champ `type` qui indique le type d'action effectuée. Les types peuvent être définis comme des constantes et importés d'un autre module. Il est préférable d'utiliser des chaînes de caractères pour les `type` plutôt que des [Symbols](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Symbol) car les  chaînes de caractères sont serialisables.

Mis à part le champ `type`, la structure de l'objet d'une action est vraiment à vous. Si vous êtes intéressé, regardez [les actions standard de Flux](https://github.com/acdlite/flux-standard-action) pour des recommandations sur la façon dont les actions doivent être construites.

Voir aussi les [actions asynchrones](#async-action) ci-dessous.

## Reducer

```js
type Reducer<S, A> = (state: S, action: A) => S
```

Un **_reducer_** (aussi appelé une *fonction réductrice*) est une fonction qui accepte une accumulation est une valeur et renvoi une nouvelle accumulation. Ils sont utilisés pour réduire une collection de valeurs à une seule valeur.

Les *reducers* ne sont pas uniques à Redux, ils constituent un concept fondamental dans la programmation fonctionnelle. Même la plupart des langages non fonctionnels, comme JavaScript, ont une API intégrée pour réduire des valeurs. En JavaScript, c'est [`Array.prototype.reduce()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce).

Dans Redux, la valeur accumulée est un objet d'état (un *state object* en anglais), et les valeurs accumulées sont des actions. Les *reducers* calculent un nouveau *state* donné par le précédent *state* et une action. Ils doivent être des *fonctions pures*, fonctions qui retournent exactement la même sortie pour des entrées données. Ils doivent aussi être exempts d'effet de bord. C'est ce qui permet des fonctionnalités intéressantes comme le rechargement à chaud (*hot reloading*) et le voyage dans le temps.

Les *reducers* sont le plus important concept de Redux.

*Ne pas mettre les appels API dans les reducers.*

## Function de dispatching

```js
type BaseDispatch = (a: Action) => Action
type Dispatch = (a: Action | AsyncAction) => any
```

Une *fonction de dispatching* (*dispatch function*) est une fonction qui accepte une action ou une [action asynchrone](#async-action); elle peut alors ou non envoyer une ou plusieurs actions au *store*.

Nous devons distinguer les fonctions de dispactching en général et la fonction de base [`dispacth`](api/Store.md#dispatch) fournie par l'instance du store sans aucun *middleware*.

La fonction de dispatch de base envoie *toujours* une action synchrone au *reducer* du *store*, avec le *state* précédent retourné par le *store*, pour calculer un nouveau *state*. Il s'attend à ce que les actions soient de simples objets prêts à être consommés par le réducteur.

Le [Middleware](#middleware) enveloppe la fonction de dispatch de base. Il permet à la fonction de dispatch de gérer les [actions asynchrones](#async-action) en plus des actions. Le middleware peut transformer, retarder, ignorer ou interpréter des actions ou des actions asynchrones avant de les transmettre au prochain middleware. Voir plus bas pour plus d'information.

## Créateur d'action

```js
type ActionCreator = (...args: any) => Action | AsyncAction
```

Un *créateur d'action* (*action creator*) est, tout simplement, une fonction qui crée une action. Ne confondez pas les deux termes, une action est une donnée utile d'information (*payload*) et un *créateur d'action* est une fabrique qui crée une action.

L'appel d'un créateur d'action ne produit qu'une action, mais ne la dispatche pas. Vous devez appeler la fonction [`dispatch`](api/Store.md#dispatch) du store pour causer la mutation. Parfois, nous disons *créateurs d'actions liées* ("*bound action creator*") pour désigner des fonctions qui appellent un créateur d'action et envoient immédiatement son résultat à une instance du *store* spécifique.

Si un créateur d'action a besoin de lire le *state* actuel, effectuer un appel API ou causer un effet secondaire, comme un changement de route, il doit renvoyer une [action asynchrone](#async-action) au lieu d'une action.

## Action Asynchrone

```js
type AsyncAction = any
```

Une *action asynchrone* est une valeur qui est envoyée à une fonction de dispatching, mais qui n'est pas prête à être consommée par le *reducer*. Elle sera transformée par un [middlware](#middleware) en une action (ou une série d'actions) avant d'être envoyée à la fonction de base [`dispatch()`](api/Store.md#dispatch). Les actions asynchrones peuvent avoir différents types, selon le middleware que vous utilisez. Elles sont souvent des primitives asynchrones, comme une Promesse ou un *thunk*, qui ne sont pas passées au *reducer* immédiatement, mais déclenchent une action de *dispatch* une fois qu'une opération est terminée.

## Middleware

```js
type MiddlewareAPI = { dispatch: Dispatch, getState: () => State }
type Middleware = (api: MiddlewareAPI) => (next: Dispatch) => Dispatch
```

Un middleware est une fonction d'ordre supérieur qui constitue une [fonction de dispatching](#dispatching-function) pour renvoyer une nouvelle fonction de dispatching. Il transforme souvent les actions asynchrones en actions.

Un middleware est composable en utilisant la composition de la fonction. Il est utile pour logguer les actions, effectuer des effets secondaires comme le routage, ou transformer un appel d'API asynchrones en une série d'actions synchrone.

Voir [`applyMiddleware(...middlewares)`](./api/applyMiddleware.md) pour un aperçu détaillé du middleware.

## Store

```js
type Store = {
  dispatch: Dispatch
  getState: () => State
  subscribe: (listener: () => void) => () => void
  replaceReducer: (reducer: Reducer) => void
}
```

Un *store* est un objet qui contient l'arbre de *state* de l'application.  
Il ne devrait y avoir qu'un seul *store* dans une application Redux, car la composition se produit au niveau du *reducer*.

- [`dispatch(action)`](api/Store.md#dispatch) est la fonction d'expédition de base décrite ci-dessus.
- [`getState()`](api/Store.md#getState) renvoi le *state* actuel du *store*.
- [`subscribe(listener)`](api/Store.md#subscribe) enregistre une fonction à appeler quand le *state* change.
- [`replaceReducer(nextReducer)`](api/Store.md#replaceReducer) peut être utilisé pour implémenter le remplacement à chaud et le fractionnement du code. Vous ne l'utiliserez probablement pas.

Voir la [référence complète de l'API](api/Store.md#dispatch) pour plus de détails.

## Créateur de *Store*

```js
type StoreCreator = (reducer: Reducer, preloadedState: ?State) => Store
```

Un créateur de *store* est une fonction qui créé un *store* Redux. Comme avec la fonction de dispatching, nous devons distinguer le créateur de *store* de base, [`createStore(reducer, preloadedState)`](api/createStore.md) exporté du paquet de Redux, des créateurs de *store* qui sont renvoyé par les exhausteurs de *store* ("*store enhancers"*).

## Exhausteur de *Store*

```js
type StoreEnhancer = (next: StoreCreator) => StoreCreator
```

Un exhausteur de *store* est une fonction d'ordre supérieur qui compose un créateur de *store* qui retourne un nouveau créateur de *store* amélioré. Ceci est similaire au middleware dans le sens qu'il vous permet de modifier l'interface du *store* de manière composable.

Les exhausteurs de store sont à peu près le même concept que les composants d'ordre supérieur dans React, lesquels sont aussi occasionelememt appelé "exhausteurs de composant" ("*component enhancers*").

Parce qu'un *store* n'est pas une instance, mais plutôt une collection de simples objets de fonctions, les copies peuvent être facilement crées et modifiées sans modifier le *store* original. Il existe un exemple dans la documentation de [`compose`](api/compose.md) qui montre ça.

Très probablement vous n'écrirez jamais un exhausteur de *store*, mais vous pouvez utiliser celui fourni par les [outils de développement](https://github.com/reduxjs/redux-devtools). C'est ce qui rend possible le voyage dans le temps sans que l'application soit au courant de ce qui se passe. De manière amusante, l'[implémentation du middleware Redux](api/applyMiddleware.md) est en lui même un exhausteur de *store*.
# Concepts clefs

Imaginez que l'état de votre application est décrit comme un simple objet. Par exemple, l'état d'une application de todo peut ressembler à ceci :

```js
{
  todos: [{
    text: 'Eat food',
    completed: true
  }, {
    text: 'Exercise',
    completed: false
  }],
  visibilityFilter: 'SHOW_COMPLETED'
}
```

Cet objet est comme un "modèle" sauf qu'il n'a pas de *setters*. C'est ainsi que différentes parties du code ne peuvent pas changer le *state* arbitrairement, ce qui provoque des bogues difficilement reproductibles.

Pour changer quelque chose dans le *state*, vous devez dispatcher une action. Une action est un objet JavaScript (remarquez comment nous n'introduisons pas de magie) qui décrit ce qui est arrivé. Voici quelques exemples d'actions :

```js
{ type: 'ADD_TODO', text: 'Go to swimming pool' }
{ type: 'TOGGLE_TODO', index: 1 }
{ type: 'SET_VISIBILITY_FILTER', filter: 'SHOW_ALL' }
```

Faites en sorte que chaque changement est décrit comme une action qui laisse une compréhension claire de ce qui se passe dans l'application. Si quelque chose change, nous savons pourquoi ça a changé. Les actions sont comme des fils d'ariane de ce qui est arrivé.
Finalement, relier le *state* est les actions ensemble, nous écrivons des fonctions appelées *reducer*. Encore une fois, rien de magique, c'est juste une fonction qui prend le *state* et l'action comme argument, et retourne le prochain *state* de l'application.
Il serait difficile d'écrire une telle fonction pour une grosse application, donc nous écrivons des fonctions plus petites qui gèrent des parties du *state* :

```js
function visibilityFilter(state = 'SHOW_ALL', action) {
  if (action.type === 'SET_VISIBILITY_FILTER') {
    return action.filter
  } else {
    return state
  }
}

function todos(state = [], action) {
  switch (action.type) {
    case 'ADD_TODO':
      return state.concat([{ text: action.text, completed: false }])
    case 'TOGGLE_TODO':
      return state.map(
        (todo, index) =>
          action.index === index
            ? { text: todo.text, completed: !todo.completed }
            : todo
      )
    default:
      return state
  }
}
```

Et nous écrivons un autre *reducer* qui gère le *state* complet de notre application en appelant ces deux *reducers* pour les clefs du *state* correspondantes :


```js
function todoApp(state = {}, action) {
  return {
    todos: todos(state.todos, action),
    visibilityFilter: visibilityFilter(state.visibilityFilter, action)
  }
}
```

Ceci est essentiellement l'idée de Redux. Notez que nous n'avons utilisé aucune API de Redux. Il est livré avec quelques utilitaires pour faciliter ce modèle, mais l'idée principale est que vous décriviez comment votre *state* est mis à jour au fil du temps en réponse à des objets d'action, et 90% du code que vous écrivez est juste du JavaScript ordinaire, sans utiliser Redux lui-même, ses APIs, ou aucune magie.

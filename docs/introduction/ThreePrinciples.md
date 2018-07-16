# Trois principes

Redux peut-être décrit en trois principes fondamentaux :

### Une seule source de vérité

**Le _[state](../Glossary.md#state)_ de toute votre application est enregistré dans une arborescence d'objet qui est dans un unique _[store](../Glossary.md#store)_.**

Cela facilite la création d'applications universelles, car l'état de votre serveur peut être sérialisé et hydraté dans le client sans effort de codage supplémentaire. Un unique arbre d'état ("state tree") facilite également le débogage ou l'inspection d'une application; il vous permet également de conserver l'état de votre application en cours de développement, pour un cycle de développement plus rapide. Certaines fonctionnalités traditionnellement difficiles à implémenter (par exemple un système d'annulation/rétablissement) peuvent soudainement devenir triviales à mettre en œuvre, si tout votre *state* est stocké dans un seul arbre.

```js
console.log(store.getState())

/* Prints
{
  visibilityFilter: 'SHOW_ALL',
  todos: [
    {
      text: 'Consider using Redux',
      completed: true,
    },
    {
      text: 'Keep all state in a single tree',
      completed: false
    }
  ]
}
*/
```

### le _State_ est en lecture seule

**La seule manière de changer le _state_ est d'emettre une [action](../Glossary.md#action), un objet qui décrit ce qui est arrivé.**

Cela garantit que ni les vues ni les appels réseau n'écriront jamais directement dans le _state_. Au lieu de cela, ils expriment une intention de transformer le _state_. Parce que tous les changements sont centralisés et se produisent un par un dans un ordre strict, il n'y a pas de condition de concurrence à surveiller. Comme les actions sont juste de simples objets, elles peuvent être journalisées, sérialisées, stockées, et rejouées plus tard pour débugger ou effectuer des tests.

```js
store.dispatch({
  type: 'COMPLETE_TODO',
  index: 1
})

store.dispatch({
  type: 'SET_VISIBILITY_FILTER',
  filter: 'SHOW_COMPLETED'
})
```

### Les modifications sont faites avec des fonctions pures

**Pour spécifier comment l'arbre de _state_ est transformé par les actions, vous devez écrire des pures [_reducers_](../Glossary.md#reducer).**

Les _reducers_ sont juste des fonctions pures qui prennent le _state_ précédent et une action, et retournent le _state_ suivant. Rappelez-vous de retourner de nouveaux objets contenant le _state_, au lieu de modifier le _state_ précédent. Vous pouvez commencer avec un seul _reducer_, et au fur et à mesure que votre application grandit, séparez les en plus petits _reducers_ qui gèrent des parties spécifiques de votre arbre de _state_. Parce que les _reducers_ ne sont que des fonctions, vous pouvez contrôler l'ordre dans lequel ils sont appelés, leur passer des données supplémentaires, ou même créer des _reducers_ réutilisables pour des tâches courantes tel que la pagination.

```js
function visibilityFilter(state = 'SHOW_ALL', action) {
  switch (action.type) {
    case 'SET_VISIBILITY_FILTER':
      return action.filter
    default:
      return state
  }
}

function todos(state = [], action) {
  switch (action.type) {
    case 'ADD_TODO':
      return [
        ...state,
        {
          text: action.text,
          completed: false
        }
      ]
    case 'COMPLETE_TODO':
      return state.map((todo, index) => {
        if (index === action.index) {
          return Object.assign({}, todo, {
            completed: true
          })
        }
        return todo
      })
    default:
      return state
  }
}

import { combineReducers, createStore } from 'redux'
const reducer = combineReducers({ visibilityFilter, todos })
const store = createStore(reducer)
```

C'est tout ! Maintenant vous savez ce qu'est Redux.

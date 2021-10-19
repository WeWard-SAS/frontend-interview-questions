# Questions:

### Pop Quizz

1) Quelle est la différence entre `==` et `===` ?

2) Quelles sont les différences et les points commun entre `var`, `let` et `const` ?

3) Qu’est-ce qu’une “closure” et comment/pourquoi en utiliser une ?

4) Est-ce que tu peux décrire ce qu'est l'event loop (boucle d’événement) en Javascript ?

5) Qu'est-ce qu'une fonction pure et pourquoi devriez-vous vous en soucier ?

6) À quoi servent les mots-clés "`async` / `await`" ?

7) Quelle est la différence entre ces quatre promesses?

```javascript
doSomething().then(function () {
  return doSomethingElse();
});

doSomething().then(function () {
  doSomethingElse();
});

doSomething().then(doSomethingElse());

doSomething().then(doSomethingElse);
```


### Code

8) Écrivez une fonction qui peut être appelée comme suit : `greet("Salut")("Louis")` et enregistrera "Salut, Louis !" sur la console ?

9) Écrivez une fonction "average" qui peut calculer la moyenne des valeurs d'un Array et qui peut être appelée depuis l'objet Array. // `[1,2,3].average()` => `2`

10) Écrivez une fonction `groupByColor()` qui groupe cette collection d'utilisateurs par `color`.

```javascript
const users = [{
  "name": "jim",
  "color": "blue",
  "age": "22"
}, {
  "name": "Sam",
  "color": "blue",
  "age": "33"
}, {
  "name": "eddie",
  "color": "green",
  "age": "77"
}];
```

11) Écrivez une fonction `flat()` capable d'aplatir un tableau de n'importe quelle profondeur ? `flat([1, [2, [3, [4]], 5]]) => [1, 2, 3, 4, 5]`


### React:

12) Que fait le hook `useEffect` ?

13) Qu'est-ce que le dom virtuel et quel problème adresse-t'il ? 

14) Qu'est-ce que la règle des hooks ?
 
15) Quelles différents types de state management as-tu déjà utilisé ?

16) UI challenge: [ici](https://codesandbox.io/s/js-ui-test-6557e)


# Réponses:

QUIZZ

1) égalité: https://developer.mozilla.org/fr/docs/Web/JavaScript/Equality_comparisons_and_sameness
2) const, let, var: https://blog.nicolas.brondin-bernard.com/quelles-sont-les-differences-entre-var-let-et-const-en-javascript/
3) Closures, https://developer.mozilla.org/fr/docs/Web/JavaScript/Closures
4) event loop: https://www.educative.io/edpresso/what-is-an-event-loop-in-javascript
5) fonctions pures: https://www.nicoespeon.com/fr/2015/01/fonctions-pures-javascript/
6) async/await: https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Statements/async_function
7) diff: https://stackoverflow.com/questions/49592105/javascript-es6-promises

CODE

8)

```javascript
function greeter(greet) {
  return (firstName) => {
    return `${greet}, ${firstName}`;
  }
}
```


9)

```javascript
Array.prototype.average = function (){
    let total = 0;

    for(let index in this) {
      total += this[index];
    }
    return total / this.length;
}
```

10) 

```javascript
function groupByColor(users) {
  const results = {};

  users.forEach((user) => {
    if (!results[user.color]) {
      results[user.color] = [];
    }    
    
    acc[user.color].push(value);
  });

  return users;
}
```

11)

```javascript
function flat(arr) {
  const flatArr = [];

  arr.forEach((value) => {
    if(Array.isArray(value)){
      flatArr.push(...flat(value));
    }
    else{
      flatArr.push(value);
    }
  });

  return flatArr;
}
```


REACT:

12) https://fr.reactjs.org/docs/hooks-effect.html
13) https://fr.reactjs.org/docs/faq-internals.html
14) https://fr.reactjs.org/docs/hooks-rules.html

# Function

Segundo a descrição da mozilla.org:

> "Funções são blocos de construção fundamentais em JavaScript. Uma função é um procedimento de JavaScript — um conjunto de instruções que executa uma tarefa ou calcula um valor. Para usar uma função, você deve defini-la em algum lugar no escopo do qual você quiser chamá-la."

Forma literal

```javascript
function minhaFuncao() {return }';
```

\-> function minhaFuncao(){} definindo uma função

\-> () paramentros

\-> (`a, b, c, ...`) argumentos, valores recebidos pela função quando ela é chamada

\-> `return`  Retorno da função

Exemplo:

Vamos criar uma função para mutiplicar dois númerosl

```javascript
function multiplicar(x, y) {
    return (x * y)
};

console.log(multiplicar(2, 5));
//10
```

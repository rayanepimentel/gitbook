# Tipo number



É uma variável tipada com número, sem "aspas".

```javascript
let num = 13;
typeof(num); // verifica o tipo de dado.
//number
```

O **number** pode ser inteiro(int) e/ flutuante(float)

```javascript
let numInteiro = 13;
let numFlutiante = 10.123456;
```

Podemos transformar uma variável em **float ou Int.**

### Int

\
Eu quero que o usuário me passe um número e que sempre ele me retorne int. Mesmo ele colocando float.\
Para isso acontecer utilizamos o **parseInt()**

```javascript
let myNumber = parseInt("Olá, me passe um número qualquer"); //(ex de um numero informado pelo usuário: 100.254868)
console.log(myNumber); // 100
```

Ou seja, ao utilizarmos **parseInt()** estamos dizendo que qualquer número após a casa decimal, não será considerado, será descartado.&#x20;

### Float

\
E se quissessimos que a variável _myNumber_ seja um number float, usariamos **parseFloat()**.\


```javascript
let myNumber = parseFloat("Olá, me passe um número qualquer"); //(ex de um numero informado pelo usuário: 100.254868)
console.log(myNumber); // 100.254868
```


# Operador ternário

O operador condicional ternário é um atalho para o condicional `if`.

```javascript
condition ? expr1 : expr2
```

* `condition` é uma expressão que é avaliada como true ou false.
* `expr1, expr2` são expressões com valores de qualquer tipo.

```javascript
let variavel = condicao ? valorSeTrue : valorSeFalse;
```

Exemplo:

```javascript
if (a > b) {
    return "a é maior que b";
} else {
    return "b é maior que a";
}
```

com operador ternário

```javascript
resultado = (a > b) ? "a é maior que b" : "b é maior que a";
```

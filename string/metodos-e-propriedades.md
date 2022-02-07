# Métodos e propriedades

Veremos alguns métodos e propriedade de strings.

### length

Para sabermos o tamanho de uma string, utilizamos a propriedade length;

```
let tam = "festa";
tam.length // 5

"xuxu".length //4
```

### IndexOf()

Retorna o primeiro índice em que o elemento pode ser encontrado.

```js
let cat = "Frajola";
cat.indexOf("a"); //vai nos retornar onde esta o primeiro a
//2
```

{% hint style="info" %}
Em Javascrit o primeiro indice será 0, o segundo 1, o terceiro 2 ...\
O indexOf também diferencia maiúsculas de minúsculas.
{% endhint %}

### LastIndexOf()

Retorna o último índice em que o elemento pode ser encontrado.

```
let cat = "Frajola";
cat.lastIndexOf("a"); //vai nos retornar onde esta o ultimo a
//6
```

## toLocaleLowerCase()

Converte a string em minúsculas

```
let cat = "Frajola";
cat.toLocaleLowerCase();
//"frajola"
```

## toLocaleUpperCase()

Converte a string em maiúsculas

```
let cat = "Frajola";
cat.toLocaleUpperCase();
//"FRAJOLA"
```

## charAt()

Passamos o índice e é retornado o caractere localizado nesse índice.

Por exemplo, queremos que retorne o caractere localizado no índice 1 da nossa variável cat.&#x20;

```
let cat = "Frajola";
cat.charAt(1);
//r
```

O caractere localizado no índice 1 de cat, é "r".&#x20;

## trim()

O trim() remove os espaços de uma variável.&#x20;

Digamos que queremos obter o username do usuário e não pode conter espaços em branco. Nesse caso utilizamos o trim();

```
let username = "Informe seu username";
// retorno do usuário: "   Joaninha     "
username.trim();
//Joaninha
```

![](<../.gitbook/assets/image (11).png>)

![](<../.gitbook/assets/image (9).png>)

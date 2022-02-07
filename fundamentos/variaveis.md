# Variáveis

### **O que são variáveis**

Quando atribuirmos um valor estamos salvando dados que podem ser acessado posteriormente.\


Variáveis podem ter qualquer nome que inclua letras, números, $ e \_, desde que não comecem com números;

### let e const

**let** é quando podemos alterar o valor da variável.&#x20;

Exemplo:\
Temos a variável **estadoMorada**, que hoje atribuimos o valor de "São Paulo".

```
let estadoMorada = "São Paulo";
```

E digamos que passou uns meses e a pessoa mudou de estado e hoje ela mora no Ceará, então seu estadoMorada não é mais "São Paulo".

```javascript
estadoMorada = "Ceará";
```

Ou seja, antes **estadoMorada** era "São Paulo"e depois "Ceará".\
Com a variável **let** é possível realizar essa mudança/atribuição de valores.

**const** é quando o valor não pode ser mudado.&#x20;

Exemplo:&#x20;

Temos a variável **estadoNascimento**, atribuída ao valor "Pará", hoje será Pará e daqui uns meses/anos também, porque não podemos mudar o local de nascimento da pessoa.

```javascript
const estadoNascimento = "Pará";
```

Ou seja, const é imutável. O valor que atribuímos a ela, sempre será o mesmo.



| variável | Exemplo                               |
| -------- | ------------------------------------- |
| let      | let endereco = 'Rua dos Bobos, nº 0'; |
| const    | const PI = 3.14;                      |

\

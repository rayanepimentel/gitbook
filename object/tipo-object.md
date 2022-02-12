# Tipo object

Um `object` pode ser criado com colchetes `{…}`com uma lista opcional de _propriedades_ . Uma propriedade é um par “chave: valor”, onde `key`é uma string (também chamada de “nome da propriedade”) e `value`pode ser qualquer coisa.

**Sintaxe:**

```
let <nome-objeto> = { key1: value1, key2: value2,...};
```

### Declarar um object

Podemos ter um obj _usuario_, que tenha os dados do _usuario_.

```
let usuario = {     // object
  name: "Ana",    // chave "name" armazena o value "Anna"
  age: 7          // chave "age" armazena o value 7
};
```

### Acessar propriedade

Para acessar uma propriedade em object usamos sempre o objeto e a chave.

**Exemplo:** Queremos saber o nome do _usuario_.

```
usuario.name // Ana

usuario["name"] // Ana
```

### Remover propriedade

Para remover uma propriedade, podemos usar `delete`

```javascript
delete usuario.age;
```

### Adicionando uma nova propriedade

Para adicionar uma nova propriedade chamamos `object` passando a `key` e atribuindo o`value`.

```
usuario.historia = "O pequeno polegar";
console.log(usuario);
// { name: "Anna", age: 7, historia: "O pequeno polegar" }
```

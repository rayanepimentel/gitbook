# Operadores de Comparação

Faz uma comparação entre valores e/ tipos e retorna true ou false.\
É como se vocês estivesse perguntando:\


```
isso é `operador de comparação` a aquilo?
- Sim (true)
ou
- Não (false}
```

* \[>] maior ou \[<] menor

```
let a = 10;
let b = 5;

let conferir = a > b; // true
let conferirNovamente = a < b; //false
```

* \[>=] maior ou igual ou \[<=] menor ou igual

```
let a = 10;
let b = 5;
let c = "10"

let conferir = a >= b; // true
let conferirNovamente = a <= b; //false
let resultado = a >= c; //true
let porqueEIgual = a <= c; //true
```

* \[==] igualdade - compara se os `valores` são iguais

```
let a = 10;
let b = 5;
let c = "10";

let conferir = a == b; //false
let conferirNovamente = a == c; //true
```

* \[!=] compara se os `valores` são diferentes

```
let a = 10;
let b = 5;
let c = "10";

let conferir = a != b; //true
let conferirNovamente = a != c; //false
```

* \[===] igualdade - compara se os `valores` e os `tipos` são iguais

```
let a = 10; //tipo number e valor 10
let b = 5; //tipo number e valor 5
let c = "10" //tipo string e valor 10
let d = 5; //tipo number e valor 5

let conferir = a === b; //false
//a e b são do tipo number, mas valores diferentes
let conferirNovamente = a === c; //false
// a e c são tipos diferentes, mas com o mesmo valores
let resultado = b === d; //true
// b e c são do mesmo tipo e tem o mesmo valor
```

* \[!==] diferente - compara se os `valores` ou os `tipos` são diferentes

```
let a = 10; //tipo number e valor 10
let b = 5; //tipo number e valor 5
let c = "10" //tipo string e valor 10
let d = 5; //tipo number e valor 5

let conferir = a !== b; //true
//a e b são do tipo number, mas valores diferentes
let conferirNovamente = a !== c; //true
// a e c são tipos diferentes, mas com o mesmo valores
let resultado = b !== d; //false
// b e c são do mesmo tipo e tem o mesmo valor
```


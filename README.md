# KOTLIN

## Comentáros
```kotlin
// uma linha

/**
* mais
* de
* uma
* linha
*/
```

## Importante!
A `fun main {}` é a porta de entrada para uma aplicação em Kotlin.
```kotlin
fun main() {
  // sentença;
}
```

## Exibir os Dados no Terminal
```kotlin
fun main() {
    println("Imprime e quebra a linha.")
    print("Imprime e continua na mesma linha.")
}
```

## Variáveis
Para declarar uma variável usar a palavra reservada `var`.  
Depois disso **definir um nome** para a variável (qualquer um).  
Junto ao nome inserir `:`, isso significa que em seguida vamos definir o **tipo de valor** que essa variável poderá receber.   
Então nós definimos o tipo, exemplo: `String`. Poderia ser `Int`, `Double`...  
Depois vem o sinal de atribuição `=`.  
Após o sinal de atribuição nós iremos passar um valor `String`, na linguagem **Kotlin** uma `String` é definida entre **aspas duplas** `"texto"`.  
E por fim, inserir `;`.  

Opcional:

1. Definir Tipo
   1. Nesse caso, o **Kotlin** define o tipo com base no valor recebido
   2. Não é necessário inserir os **dois pontos** após o nome definido para a variável
2. **Ponto e vírgula**

```kotlin
fun main() {
    var nome: String = "Weverton";
}
```

Podemor declarar uma variável e atribuir seu valor em alguma linha seguinte. Nesse caso é **obrigatório** definir o tipo.

```kotlin
fun main() {
    var nome: String;
    nome = "Weverton";
}
```

*Por padrão* em Kotlin uma variável não pode receber como valor **nulo**, caso isso aconteca o seu programa vai gerar um **erro**.  
Para que isso não ocorra podemos usar o sinal de interrogação **?** na declaração da variável, esse sinal habilita a possibilidade de uma variável receber o valor **Nulo**.  
```kotlin
fun main() {
    var nome : String? = null;
}
```

Com a palavra reservada `Any`, declaramos uma variável que pode receber um valor de qualquer **tipo**, pois `Any` é a classe mãe de todos os tipos.  
A palavra reservada `as`, faz um **CAST** (converte para o **tipo** desejado). Mas se o valor não for do tipo que fizermos o **CAST** vai gerar um erro no programa, para fazer um **CAST** seguro usamos a interrogação `?`.
Já a palavra reservada `is` diferente do `as` só faz o **CAST** se for possível, dispensando assim o uso da interrogação `?`.
```kotlin
fun main() {
    var valor:Any = "Weverton";    
    if ((valor as? Int) != null) println(valor);
    
    valor = 8;
    if ((valor as? Int) != null) println(valor);
    
    valor = 25;
    if (valor is String) println(valor);
    else if (valor is Int) println(valor);
}
```

## Constantes
Para declarar uma variável usar a palavra reservada `val`.  
Os demais conceitos é o mesmo para a criação de uma variável.  
"Lembrando que uma contante não pode ter seu valor alterado".

## Template String
É o ato de interpolar uma String colocando uma variável dentro dela, sem a variável perder a funcionalidade de seus atributos se assim possuir.
```kotlin
fun main() {
    var nome: String = "Weverton";
    
    // Concatenação simples
    var mensagemFinal: String = "Olá, " + nome;
    
    // Template String
    mensagemFinal = "Seja bem vindo, $nome";
    
    // Template String: acessando atributos de uma variável ou objeto
    mensagemFinal = "O tamanho dessa String é ${nome.length}"; 
}
```

## Estrutura de Controle: IF, ELSE IF & ELSE
```kotlin
fun main() {
    var uf: String = "sp";
    
    if (uf == "sp") {
        println("São Paulo.");
    } else if (uf == "rj") {
        println("Rio de Janeiro.");
    } else {
        println("Outro Estado brasileiro.");
    }
    
    // Caso as sentenças use somente uma linha, podemos remover o par de chaves e deixar inline
    uf = "ba";
    
    if (uf == "sp") println("São Paulo.");
    else if (uf == "rj") println("Rio de Janeiro.");
    else println("Outro Estado brasileiro.");
}
```

## Operador Ternário
```kotlin
fun main() {
	if (5 % 2 == 0) println("PAR") else println("ÍMPAR");
}
```

## Listas
### ArrayList
É uma lista mutável, isso quer dizer que nós podemos adicionar e remover elementos.
```kotlin
fun main() {
    var minhaLista: ArrayList<Int> = ArrayList<Int>();
    
    minhaLista.add(1);
    minhaLista.add(2);
    minhaLista.add(3);
    
    println(minhaLista);
    
    minhaLista.remove(2);
    
    println(minhaLista);
}
```

### mutableListOf
A diferença dessa **lista** para a de cima é que podemos criá-la já passando os parâmetros.
```kotlin
fun main() {
    var minhaLista = mutableListOf<Int>(1, 2, 3);
    
    minhaLista.add(4);
    minhaLista.add(5);
    minhaLista.add(6);
    
    println(minhaLista);
    
    minhaLista.remove(2);
    
    println(minhaLista);
}
```

### listOf
Não é mutável, quer dizer que não pode ser alterada, não poder adicionar ou remover elementos.
```kotlin
fun main() {
    var minhaLista = listOf<Int>(1, 2, 3);
    
    println(minhaLista);
}
```

## Estrutura de Repetição: FOR
```kotlin
fun main() {
    var minhaLista = listOf<Int>(1, 2, 3);
    
    for (numero in minhaLista) {
        println(numero);
    }
    
    // inline
    for (numero in minhaLista) println(numero);
}
```

Contar a até 10
```kotlin
fun main() {    
    for (numero in 1..10) println(numero);
}
```

## Funções

Para declar uma **função** na linguagem Kotlin devemos usar a palavra reservada `fun` seguido de um par de parênteses `()` e depois um par de chaves `{}` para representar o corpo da função.
```kotlin
fun minhaFuncao() {    
    // sentença;
}

fun main() {    
    // Incovanco a função
    minhaFuncao();
}
```

### Função lambda
Na linguegem Kotlin uma função Lambada é definida dentro de uma par de chaves `{}`.
```kotlin
fun main() {
    var funcaoLambda = { n1: Int, n2: Int -> n1 + n2 };
    println(funcaoLambda(3, 6));
    
    var outraFuncaoLambda = { n: Int -> n * 5 };
    println(outraFuncaoLambda(3));
}
```

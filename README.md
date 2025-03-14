# lista-ponderada
ponderada semana 6

# Instruções
- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 8 questões objetivas assinalando a alternativa correta e **justificando sua resposta.**
- Resolva as 2 questões dissertativas escrevendo no próprio arquivo .md
- Lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com o uso de ChatGPT (e similares), pois entregar algo só para ganhar nota não fará você aprender. Não seja dependente da máquina!
- Ao final, publique seu arquivo lista_01.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
a) A saída será undefined seguido de erro 

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log

Resposta: Alternativa correta: A

a) A saída será undefined seguido de erro

Justificativa:

O var x é (hoisting), mas sem valor, então console.log(x) imprime undefined.
O let y também é içado, mas fica na "zona temporal morta" até sua inicialização. Tentar acessá-lo antes da declaração gera um erro.



**2) O seguinte código JavaScript tem um erro que impede sua execução correta. Analise e indique a opção que melhor corrige o problema. Justifique sua resposta.**

```javascript
function soma(a, b) {
    if (a || b === 0) {
        return "Erro: número inválido";
    }
    return a + b;
}
console.log(soma(2, 0));
```

a) Substituir if (a || b === 0) por if (a === 0 || b === 0)

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

2)Resposta: Alternativa correta: A

a) Substituir if (a || b === 0) por if (a === 0 || b === 0)

Justificativa:

a || b === 0 verifica apenas se b é 0, pois === tem prioridade sobre ||.
A condição correta para verificar se qualquer um dos valores é 0 é a === 0 || b === 0.


______
**3) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
function calcularPreco(tipo) {
    let preco;

    switch(tipo) {
        case "eletrônico":
            preco = 1000;
        case "vestuário":
            preco = 200;
            break;
        case "alimento":
            preco = 50;
            break;
        default:
            preco = 0;
    }

    return preco;
}

console.log(calcularPreco("eletrônico"));
```

a) O código imprime 1000.

b) O código imprime 200.

c) O código imprime 50.

d) O código gera um erro.

3) Resposta: Alternativa correta: B

b) O código imprime 200

Justificativa:

O case "eletrônico" não tem break, então ele continua a execução e redefine preco para 200 no case "vestuário", antes do break.
Isso faz com que o retorno seja 200.


______
**4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);
```
a) 0

b) 6

c) 18

d) 24


4) Resposta: Alternativa correta: C

c) 18

Justificativa:

map(x => x * 2): transforma [1, 2, 3, 4, 5] em [2, 4, 6, 8, 10].
filter(x => x > 5): mantém [6, 8, 10].
reduce((a, b) => a + b, 0): soma 6 + 8 + 10 = 18.

______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

c) ["banana", "abacaxi", "manga", "laranja"]

d) ["banana", "maçã", "uva", "abacaxi", "manga"]

5) Resposta: Alternativa correta: C

c) ["banana", "abacaxi", "manga", "laranja"]

Justificativa:

splice(1, 2, "abacaxi", "manga"): remove 2 elementos a partir do índice 1 ("maçã" e "uva") e insere "abacaxi" e "manga".

______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.


6) Resposta: Alternativa correta: A

a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.

Justificativa:

A herança permite o compartilhamento de métodos/propriedades entre classes.
Em JavaScript, isso é feito com extends, que permite que uma classe herde outra.


______
**7) Dado o seguinte código. Indique a alternativa correta e justifique sua resposta.**

```javascript
class Pessoa {
  constructor(nome, idade) {
    this.nome = nome;
    this.idade = idade;
  }

  apresentar() {
    console.log(`Olá, meu nome é ${this.nome} e tenho ${this.idade} anos.`);
  }
}

class Funcionario extends Pessoa {
  constructor(nome, idade, salario) {
    super(nome, idade);
    this.salario = salario;
  }

  apresentar() {
    super.apresentar();
    console.log(`Meu salário é R$ ${this.salario}.`);
  }
}
```


I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente.  
II) O método `apresentar()` da classe Funcionario sobrepõe o método `apresentar()` da classe Pessoa, mas chama o método da classe pai usando `super`.  
III) O código não funciona corretamente, pois Funcionario não pode herdar de Pessoa como uma classe, já que o JavaScript não suporta herança de classes.

Quais das seguintes afirmações são verdadeiras sobre o código acima?

a) I e II são verdadeiras.

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

7) Resposta: Alternativa correta: A

a) I e II são verdadeiras.

Justificativa:

I) Verdadeiro: Funcionario herda Pessoa, então pode acessar nome e idade.
II) Verdadeiro: apresentar() de Funcionario chama super.apresentar(), que executa o método da classe Pessoa, antes de imprimir o salário.
III) Falso: JavaScript suporta herança de classes.


______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

b) A asserção é verdadeira e a razão é falsa.

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

8) Resposta: Alternativa correta: B

b) A asserção é verdadeira e a razão é falsa.

Justificativa:

Asserção verdadeira: Polimorfismo permite que diferentes classes respondam ao mesmo método de formas distintas.
Razão falsa: JavaScript não suporta sobrecarga de métodos (métodos com mesmo nome e parâmetros diferentes). Ele suporta sobrescrita (redefinir métodos em subclasses).


______

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
function somaArray(numeros) {

    for (i = 0; i < numeros.size; i++) {
        soma = 2*numeros[i];
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```

Resposta: 

function somaArray(numeros) {
    let soma = 0; // Inicializa a soma corretamente

    for (let i = 0; i < numeros.length; i++) { // Usa "let" para declarar i e "length" para o tamanho do array
        soma += 2 * numeros[i]; // Soma o dobro de cada número ao total
    }
    return soma; // Retorna a soma correta
}
console.log(somaArray([1, 2, 3, 4])); // Saída esperada: 20


Correções:

soma foi inicializado corretamente.
i agora é declarado com let.
numeros.size foi corrigido para numeros.length.
soma = 2 * numeros[i]; foi alterado para soma += 2 * numeros[i];, pois o código anterior sobrescrevia o valor de soma a cada iteração.




______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.


 Resposta:

class Produto {
    constructor(nome, preco) {
        this.nome = nome;
        this.preco = preco;
    }

    calcularDesconto() {
        return this.preco * 0.9; // Aplica 10% de desconto
    }
}

class Livro extends Produto {
    calcularDesconto() {
        return this.preco * 0.8; // Aplica 20% de desconto para livros
    }
}

let celular = new Produto("Celular", 1000);
let livro = new Livro("Livro de JavaScript", 100);

console.log(celular.calcularDesconto()); // 900
console.log(livro.calcularDesconto()); // 80



Explicação:

Produto tem os atributos nome e preco, e um método calcularDesconto() que aplica 10% de desconto.
Livro herda Produto, mas sobrescreve calcularDesconto() para aplicar 20% de desconto.
super não foi necessário, pois o método foi completamente substituído.











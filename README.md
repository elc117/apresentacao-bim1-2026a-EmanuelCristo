# Tuplas em Haskell e Diferentes Linguagens

Tuplas são estruturas de dados que permitem agrupar um conjunto fixo de elementos em uma única unidade. 
Diferente das listas, elas são projetadas para armazenar valores de tipos diferentes (heterogêneos) e costumam ser imutáveis após a criação.

## Haskell: Utiliza parênteses `()` com elementos separados por vírgulas `,`

```Haskell
type Tupla = (String, String, Int)  
exemplo :: Tupla  
exemplo = ("exemplo", "Tuplas", 1)
```
Características: imutável e o acesso aos elementos é feito através de funções específicas (como fst e snd para pares) ou, mais comumente, via **Pattern Matching**.

### Funções Relacionadas
*`fst`: Extrai o primeiro elemento de um par.

*`snd`: Extrai o segundo elemento de um par.

*`zip`: Combina duas listas em uma lista de tuplas. Ex: `zip [1,2] ['a','b']` vira `[(1,'a'), (2,'b')]`.

*`unzip`: Transforma uma lista de tuplas em duas listas separadas.

---
## Python: É representada por uma sequência de itens separados por vírgula `,` 
O uso de  parênteses `()` na definição da tupla não é obrigatório, mas fortemente
recomendado.

```Python
tupla = 'exemplo', 'tupla', 1 
```
Forma usual

```Python
tupla = ('exemplo', 'tupla', 1)
```
Características: imutável e o acesso aos elementos é feito através de índices numéricos (ex: `tupla[0]`, `tupla[-1]`) ou por descompactação (ex: `a, b, c = tupla`).

### Funções
*`count(valor)`: Conta quantas vezes um valor aparece na tupla.

*`index(valor)`: Retorna a posição da primeira ocorrência de um valor.

*`len(tupla)`: Retorna o número de elementos.

---
## C#: Nessa linguagem existe dois "tipos" de tuplas:  
#### A classe `Tuple` (maneira "antiga"), sendo uma **classe de referência**
```C#
var tupla = new Tuple<string, String, int>("Exemplo", "Tupla", 1);
```
Ou
```C#
var tupla = Tuple.Create("Exemplo", "Tupla", 1);
```
Caracteristicas: imutável, alocação na **Heap** e o acesso a emelentos é feito apenas unsando `.Item1`, `.Item2`, etc.  

#### `ValueTuple` (maneira moderna), sendo uma **estrutura de valor**
```C#
var tupla = ("Exemplo", "Tupla", 1);
```
Com nomes
```C#
(string Tipo, string Nome, int Quantidade) TuplaModerna = ("Exemplo", "Tupla", 2);
```
Caracteristicas: mutável (exceto se os valores forem `readonly`), alocação na **Stack** e o acesso aos elementos pode ser feito usando `.Tipo` ao invés de `.Item1` (melhor compreensão).

### Funções
*`ToTuple()`: Converte uma ValueTuple na classe Tuple antiga.

*`Deconstruct()`: Método que permite que objetos de classes sejam "quebrados" em tuplas.

*`Equals()`: Tuplas em C# possuem comparação por valor nativa (duas tuplas com os mesmos dados são consideradas iguais).

---
## TypeScript: Declarada usando colchetes`[]` e separada por vírgulas`,` 

```TypeScript
let tupla: [string, string, number];
tupla = ["Exemplo", "Tupla", 1];
```
Tupla Nomeada
```TypeScript
type Registro = [tipo: string, nome: string, qtd: number];
const item: Registro = ["Exemplo", "Tupla", 2];
```
Características: mutável por padrão (exceto se usar o modificador `readonly`). O acesso é feito por índices numéricos (ex: `tupla[0]`)

### Funções  
As funções são as mesmas de um Array, mas o tipo restringe o uso:  
*`map() / forEach()`: Para iterar sobre os elementos (embora exija cuidado com tipos diferentes).

*`Desestruturação`: `const [a, b] = minhaTupla;` é a forma principal de "uso"

## Usos

Utilize tuplas quando você souber com antecedência que muitos componentes contêm algumas partes de dados já esperadas, e quando tiver dados que não devem ser alterados pelo programa, isso torna seu código mais seguro e ligeiramente mais rápido em termos de performance.  
As tuplas podem ser utilizadas para modelar itens do mundo real, como coleções de itens.
Por exemplo, uma pessoa pode ser representada por seu nome, telefone, endereço e ano
de nascimento. Desta forma, a tupla é formada por valores de tipos diferentes:

```Haskell
maria :: (String, String, String, Int)
maria = ( "Maria Silva", "222-2222", "Rua A, 35", 1998)
```

# Tuplas em Haskell e Diferentes Linguagens

tuplas são estruturas de dados que permitem agrupar um conjunto fixo de elementos em uma única unidade. 
Diferente das listas, elas são projetadas para armazenar valores de tipos diferentes (heterogêneos) e costumam ser imutáveis após a criação.

## Sintaxe

Haskell: Utilizam parênteses `()` com elementos separados por vírgulas `,`

```Haskell
type Tupla = (String, String, Int)  
exemplo :: Tupla  
exemplo = ("exemplo", "Tuplas", 1)
```

## Usos

Utilize tuplas quando você souber com antecedência que muitos componentes contêm algumas partes de dados já esperadas.  
As tuplas podem ser utilizadas para modelar itens do mundo real, como coleções de itens.
Por exemplo, uma pessoa pode ser representada por seu nome, telefone, endereço e ano
de nascimento. Desta forma, a tupla é formada por valores de tipos diferentes:

```Haskell
maria :: (String, String, String, Int)
maria = ( "Maria Silva", "222-2222", "Rua A, 35", 1998)
```

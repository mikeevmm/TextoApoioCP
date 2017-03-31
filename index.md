# Introdução Fundamental À Programação

## Introdução

Em geral, aprender os princípios de porgramação é um processo de tentativa e erro.

É possível estudar, no sentido académico mais típico, as estruturas mais
concretas ou abstratas presentes na programação, mas o fundamental já se
encontra nessa altura profundamente interiorizado -- um pouco como na matemática
ou física já há muito se ultrapassaram os conceitos algébricos básicos.

No entanto, por vezes este facto pode ser ignorado por professores de cadeiras
de introdução à programação, para os quais conceitos tão sedimentados são por
vezes esquecidos. Por outro lado, manuais pedagógicos de programação podem
frequentemente ser morosos ou substimar o conhecimento prévio matemático do leitor.

E nem sempre é fácil aprender programação por tentativa e erro quandonão há tempo,
ou especial motivação.

Assim, nesta sebenta pretende-se fazer uma introdução prática aos conceitos
fundamentais de programação, procurando não esquecer que o conhecimento prévio é
sobretudo na área da matemática, e que se pretende adquirir sobretudo
conhecimento prático.

Pague-me um café em `http://ko-fi.com/A776VK1` :)

## O Que é uma Linguagem de Programação

Apesar de soar filosófico, uma pergunta pertinente será em que consiste uma
linguagem de programação e, sobretudo, o que permite fazer.

Sucintamente, uma linguagem de programação consiste, como em qualquer linguagem,
num conjunto de vocabolário e regras gramaticais (designado **sintaxe**) que
permite comunicar um conjunto de intenções; neste caso ao computador.

Por exemplo, suponhamos `1 + 3` (uma "frase" legítima em Python): trata-se de um
conjunto de 3 "palavras", duas delas números e uma um operador matemático,
que tanto denota `a soma de um e três` como o número ("palavra") `4`.
A regra gramatical manifesta-se no facto de `+ 1 3` não fazer sentido.

Assim, uma linguagem de programação permite-nos definir um conjunto de ações
a tomar pelo computador, o que permite automatizar tarefas (tratamento de dados),
ou criar comportamentos complexos (simulação, jogos).

## O Que é Python e Como o Instalar

>Este capítulo é irrelevante se já tiver instalado `Python`, **verificando que
>a sua instalação não é de Python 2**.
>
>Para isso, abra uma linha de comandos (Windows) ou terminal (MacOS, Linux)
>e escreva `python` (seguido de `enter`).
>Se uma instalação já estiver presente, poder-se-á ler a versão instalada
>na máquina; caso contrário dever-se-á observar um erro.

Python trata-se de uma linguagem de programação simples, recomendada para
principiantes pela sua sintaxe próxima do inglês, e abstração de operações,
ou seja, pelo facto de muitas operações comuns de realizar (e por vezes não
triviais de implementar) estarem já embutidas na língua.

Apesar disto, é extremamente poderosa, sendo por isso muito utilizada por hackers,
académicos, ou para prototipar ou desenvolver ferramentas (onde a performance
não é crítica).

Prolongando o paralelismo entre Python e uma linguagem comum, é necessário
"ensinar" ao computador a interpretar código Python; instalar Python.
Tal pode ser feito em `python.org`, onde instaladores se encontram disponíveis
para download.

>Uma vez que o *layout* do site oficial muda frequentemente, não se considerou vantajoso
>detalhar o processo de instalação.
>Aquando da escrita deste texto, o instalador é obtido na tab *Downloads*,
>onde é possível fazer download de Python 3.6.1 (referido como Python3) ou
>2.7.13 (referido como Python2), sendo que nos interessa o primeiro.

O instalador inclui também o editor de código IDLE, normalmente utilizado na
cadeira de CP.

---

## Variável (*Variable*)

Um dos conceitos que poderá ser ambíguo para estudantes da área da matemática é
o conceito de variável.

Como se verificará ao longo deste texto, os conceitos associados a programação
são normalmente muito mais atómicos (básicos) do que o correspondente matemático.

Trata-se do caso aqui: designa-se simplesmente por variável uma entidade que
contenha um valor, e que possa ser acessada como tal. Nem sempre será sinónima
do valor que contém (como se verá mais à frente), mas é muitas vezes esse o caso.

Em Python, uma variável é definida quando lhe é atribuída um valor. No IDLE:

```python
>>> x = 3
```

A variável `x` contém agora o valor `3`, podendo ser chamada, obtendo-se o valor
correspondente:

```python
>>> x
3
```

Podemos manipular variáveis, obtendo novos valores, ou mudar o valor da variável:

```python
>>> x = 3
>>> x
3
>>> x + 1
4
>>> x
3
>>> x = x + 1
>>> x
4
```

Existem restrições aos nomes de variáveis, nomeadamente:

+ Não podem conter espaços; `x y` seria intrepretado como duas variáveis, `x` e `y`.

+ São *case-sensitive*, isto é, maiúsculas e minúsculas **não** são irrelevantes.
 `X` ≠ `x`.

+ Não podem começar com um dígito, embora possam conter dígitos. `a1` é válido,
 enquanto que `1a` não.

+ Apenas podem conter os caracteres alfanuméricos normais; letras, números, e *underscores*.

## Comentários

Um comentário trata-se, à partida, de um pedaço de código ignorado na execução
do programa.

Do ponto de vista prático, comentários são particularmente úteis na manutenção
de código a longo termo, permitindo adicionar notas explicando o raciocínio ou
utilização do programa, assim como comportamentos ou valores esperados.

Comentários são delimitados à esquerda por um cardinal (`#`), e extendem-se até ao
fim da linha. Podem seguir código a ser executado.

Por exemplo:

```python
a = 3 # Todo o texto seguinte é ignorado.
# a = 4
# a continua a possuir o valor 3
```

Ao longo deste texto, comentários serão também usados como acima, isto é, para adicionar
informação contextualmente, sem que se deva atribuir valor programático ao texto.

## Tipos (*Types*)

>A secção que se segue poderá ser intimidadora ou morosa numa primeira aproximação;
>é sugerido que a sua leitura seja efetuada de uma forma leve, revisitando cada
>secção posteriormente quando necessário, enquanto o seu conceito não estiver fixado.

Os valores podem ser de tipos difrentes. A manifestação mais direta deste facto
surge na comparação de elementos, que normalmente só pode ser efetuada entre
dois elementos do mesmo tipo.

Por exemplo, `1 > 2` é verdadeiro, mas qual o significado da comparação `"a" > 2`
(onde `"a"` é a letra)?

Em Python, há um número de tipos já definidos, dos quais falaremos dos mais relevantes.

### String (*Fio* (de letras))

Como já vimos, uma série de caracteres alfanúmericos (letras) define não
uma sequencia textual, mas sim uma variável.

Mas como fazer para definir texto, no sentido literal?

A um conjunto de caracteres delimitado por um par de aspas (*quotes*, `"`)
ou plicas (*single quotes*, `'`), chama-se uma `string`, e define, precisamente,
um pedaço de texto. Podemos atribuir esse valor a uma variável:

```python
>>> x = 'hello world!'
>>> x
'hello world!'
```

>Conseguir que uma máquina "diga" *Hello World* é um dos exercícios mais celebrados
>e é normalmente utilizado como o exercício (relevante) mais básico possível,
>assim como uma boa métrica da complexidade da linguagem.

Strings funcionam como [listas](#list-lista), na medida em que cada letra pode
ser acedido pelo seu índice, como elementos da `string`.

```python
>>> x[0]
'h'
```

### Int (*inteiro*, *integer*)

Como o nome indica, um `int` é o tipo correspondente a valores inteiros.
A sua definição é subtil, pois o tipo `float` (que veremos já a seguir) pode também
definir um qualquer valor inteiro; a diferença está no facto de um `int` verdadeiramente
*não ter a capacidade* de definir um valor que não inteiro.

>A diferença entre `int` e `float` encontra-se muito mais presente em Python2,
>onde o quociente entre dois inteiros era *sempre* ainda um inteiro.
>Este comportamento levava de tal forma a erros dissimulados que foi simplesmente
>removido em Python3.

Vimos já multiplos exemplos de variáveis com tipos `int`:

```python
>>> x = 3
>>> x
3
```

A noção mais formal de `int` depende de como o seu valor é guardado na memória
do computador, de um ponto de vista mais técnico. Essa questão encontra-se
abordada na seccção [referente a memória](#valores-e-memória).

>Na opinião do autor, as questões de memória e arquitetura surgem naturalmente
>numa fase posterior, em que começam a aparecer preocupações com optimização.
>
>No entanto, esta matéria é por vezes introduzida no início do semestre, pelo
>que o capítulo correspondente procura ser auto-contido e pode ser lido desde já.

### Float (*floating point*, *ponto flutuante*)

O tipo `float` também representa um número mas como o nome *ponto flutuante* indica,
de certa forma, este possui uma natureza fracional; entre `3.14159` e `314.59`
o ponto "flutua".

Em termos práticos, um `float` representa um valor decimal, com uma precisão limitada
(ver [Representação de Valores e Memória](#valores-e-memória)).

Pode ser declarado explicitamente, ou resultar da divisão de dois `int`s:

```python
>>> 1.51
1.51
>>> 3/5
0.6
```

É de notar, ainda, que a soma de um `int` com um `float` resulta ainda num `float`
(como esperado):

```python
>>> 1.513 + 2
3.513
```

### List (*lista*)

Uma lista pode ser descrita como um conjunto **ordenado** de elementos, que
**poderão ou não** ser repetidos.

Trata-se de um conceito fundamental na programação, sendo que muitos exercícios dependem
fundamentalmente do conceito de lista.

Uma lista, sintáticamente, é delimitada por dois parentesis retos (`[ ]`), e os seus
elementos são separados por vírgulas. Estes elementos podem ser de qualquer tipo,
sendo que uma lista pode conter elementos de diferentes tipos (incluindo listas),
ou outras variáveis (sendo usado o seu valor).

Acede-se aos elementos de uma lista pelo seu índice, sendo que o primeiro elemento
tem índice `0`, o segundo `1`, ..., de acordo com a sintaxe `list[index]`.

>A questão do *zero indexed* (primeiro índice 0 e consequentes) ou *one indexed*
>(primeiro índice 1 e consequentes) é fonte, compreensivelmente, de protesto.
>
>A razão para o *zero index* ser a norma não é apenas histórica; de um
>ponto de vista prático, muitas das sucessões consideradas são tais que é
>conveniente ter o índice a variar de `0...i`.

Os elementos de uma lista podem ser alterados, como se fossem uma variável.
Diz-se, por isso, **mutável**.

Por exemplo:

```python
>>> l = ['some text', 3, 2.14]

>>> l
['some text', 3, 2.14]

>>> l[0]
'some text'
>>> l[3]
Erro

>>> x = 3.14
>>> l = [x, x]
>>> l
[3.14, 3.14]

>>> l = [1, 2, 3]
>>> l[0] = 0
>>> l
[0, 2, 3]
```

### Tuple (*tupla*)

Uma tupla é semelhante a uma lista, mas cujos elementos são imutáveis, isto
é, não podem ser alterados.

É delimitada por parêntesis curvos (`( )`), sendo que se define uma tupla vazia
como `(,)`, a fim de desambiguar de uma expressão entre parêntesis.

Os elementos numa tupla podem ser de qualquer tipo (incluindo outras tuplas),
sendo separados por vírgulas.
O acesso aos mesmos é efetuado da mesma forma que para uma lista.

Por exemplo:

```python
>>> x = ( 1, 'a', ('b', 2) )
>>> x
(1, 'a', ('b', 2))
>>> x[0]
1
>>> x[2]
('b', 2)
>>> x[2][0]
'b'
```

### Set (*conjunto*)

Um `set` representa um conjunto no sentido matemático tradicional.

A ordem dos seus elementos é **irrelevante**, e não pode possuir o mesmo
elemento mais do que uma vez.

É delimitado por chavetas (`{ }`), embora tenha de possuir elementos na sua
declaração (sendo que caso contrário se declarou um dicionário).

Por exemplo:

```python
>>> {3,1,2}
{1, 2, 3}

>>> {1,1,1}
{1}
```

### Dictionary (*dicionário*)

Um dicionário faz corresponder a um elemento, a **key** (*chave*), outro elemento,
**value** (*valor*), sendo que o tipo de qualquer do valor é arbitrário
(podendo, de facto, ser um outro dicionário).

>O tipo da chave não é, na verdade, de todo arbitrário, tendo esta de ser *hashable*.
>Isto significa que elementos mutáveis, como listas ou dicionários, não podem ser
>usados como chaves em dicionários, sendo que tal resulta no erro
>`TypeError: unhashable type`.
>
>Esta questão é discutida mais a fundo no apêndice [Hashable Elements](#hashable-elements).

São declarados com chavetas (`{ }`), e opcionalmente já com chaves e valores correspondentes,
de acordo com a sintaxe

```python
{ chaveA : valorA, chaveB : valorB }
```

Acede-se aos valores pela chave correspondente, sendo que a sintaxe correspondente
é semelhante ao da lista. Tomando um novo exemplo, já com valores:

```python
>>> d = {} # Dicionário vazio
>>> d = {'a' : 1, 'b' : 2}
>>> d['a']
1
>>> x = d['b']
>>> x
2
```

Por razões óbvias, as chaves deverão ser únicas (pois a referência a um valor tornar-se-ia
ambígua), mas não há qualquer restrição aos valores.

### Exercícios

#### 1. Como representar uma lista telefónica

Um dicionário é frequentemente comparado com uma lista telefónica. Suponhamos os
seguintes nomes e números:

```text
Adolfo Dias             263779913

Oscar Allonso           249113132

Jose Aguiar de Mota     251998195

Henrique Olhao          229505463
```

>Ignoramos para já acentuação, uma vez que tal introduz complicações, discutidas
>mais tarde neste texto.

Estes dados podem facilmente ser guardados num dicionário, para
posterior acesso. Representemos os nomes como `string`s, e os números de
telefone como `int`s:

```python
{
    'Adolfo Dias' : 263779913,
    'Oscar Alhonso' : 249113132,
    'Jose Aguiar de Mota' : 251998195,
    'Henrique Olhao' : 229505463
}
```

>Em Python, ao contrário do que se verifica noutras linguas, o espaçamento
>é muito relevante, como se verá à frente.
>
>No entanto, na declaração de elementos como `list`s, `tuple`s ou `dictionary`s,
>o espaçamento usado é, normalmente, irrelevante, sendo sobretudo uma
>questão estética.

Supondo que este dicionário se encontra atribuido à variável `d`,

```python
>>> d['Adolfo Dias']
263779913
```

## Scripts

>A noção de *script* não pertence especificamente a Python, nem é necessariamente
>formalmente um conceito de programação, mas poderá ser confundida com o uso da shell
>numa primeira aproximação, pelo que aqui se refere.

Até agora tem-se apresentado como exemplo comandos únicos numa *shell* de Python.

>Uma *shell* é uma interface onde o utilizador pode fornecer
>comandos e observar o seu resultado, interagindo com o mesmo.

Em geral, é mais interessante designar, à partida, um conjunto de instruções
a executar, podendo correr o programa de uma só vez.

A estes ficheiros é dado o nome `script`.

Um script de Python é qualquer ficheiro com a terminação `.py`.

Na prática, é comum recorrer ao IDLE para escrever scripts.
`File > New File` cria um novo ficheiro, que pode ser guardado em
qualquer local. Este pode depois ser corrido em `Run > Run Module`,
ou carregando `F5`.

---

## Funções

TODO

## Valores e Memória

TODO

## Apêndices

### Hashable Elements

Em termos mais matemáticos, um dado tipo é *hashable* se existir uma aplicação
(no sentido matemático) `H` cuja aplicação a um qualquer valor (*hash*)
é sempre injetiva (se for corretamente construido).

Ou seja, um tipo é *hashable* se para cada elemento existir uma um elemento
identificativo que seja único e não mude.

Torna-se então mais intuitivo justificar que as chaves de um dicionário tenham
de ser elementos *hashable*; supondo que a um elemento `K` (*key*) associamos
um valor `V`, com `K` *hashable* e hash `H(K)`, temos, esquematicamente:

```math
D : H(K) ---> V
```

Assim, quando procuramos o valor associado a `K`,

```math
D(K) = D[ H(K) ] = V
```

Se o elemento `K` não puder ser coerentemente transformado por `H`, o que
se verifica para objetos mutáveis, este processo é impossível, pelo que se
justifica que não possam ser chaves em dicionários.

[Mais informação sobre Hash Functions.](https://en.wikipedia.org/wiki/Hash_function)
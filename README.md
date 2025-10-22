# PseudoScript: Uma Linguagem de Programação para quem quer aprender lógica

O PseudoScript é projetado para ser um ponto de partida para iniciantes. Após dominar os conceitos básicos, os aspirantes podem fazer uma transição mais fácil para a programação real em JavaScript ou Python. Ele fornece uma base sólida em lógica, estruturas de controlo e resolução de problemas sem sobrecarregar os iniciantes com uma sintaxe complexa.

<details>
    <summary>Escopo</summary>

Escopo funcaoine a região do programa onde uma variável, função ou constante pode ser acessada e utilizada. É como uma "zona de visibilidade" para elementos do código.
O escopo determina:

- ✅ Onde uma variável pode ser usada
- ✅ Quando ela existe na memória
- ✅ Quem pode acessá-la
- ❌ Onde ela NÃO pode ser acessada (fora do escopo)

### Principais Tipos de Escopo

<details>
    <summary>Escopo Global</summary>
A variável é acessível em qualquer parte do programa.

```python
# Variável global
mensagem = "Olá, mundo!"

funcao funcao1():
    imprime(mensagem)  # ✅ Tem Acesso

funcao funcao2():
    imprime(mensagem)  # ✅ Tem Acesso

funcao1()  # Olá, mundo!
funcao2()  # Olá, mundo!
imprime(mensagem)  # ✅ Olá, mundo!
```

</details>
<details>
    <summary>Escopo Local</summary>

A variável existe apenas dentro de um bloco específico (função, if, loop, etc).

```python
funcao minha_funcao():
    variavel_local = "Eu sou local"
    imprime(variavel_local)  # ✅ Funciona

minha_funcao()  # Eu sou local
imprime(variavel_local)  # ❌ ERRO: variavel_local não está funcaoinida
```

</details>

<details>
    <summary>Escopo de Bloco</summary>
A variável existe apenas dentro de um bloco condicional ou loop.

```python
se verdadeiro:
    valor = 10  // Escopo de bloco
    imprime(valor)  // ✅ 10

imprime(x)  // ❌ ERRO: x não está funcaoinida
```

</details>
<details>
    <summary>Escopo de Função</summary>
A variável é acessível em toda a função onde foi declarada.

```python
funcao exemplo():
    pontos = 20
    
    se pontos:
        imprime(pontos)  # ✅ Acede 'pontos' da função

    enquanto pontos >= 0:
        imprime(pontos)
        repeticao = repeticao - 1  # ✅ Acede 'pontos' da função

exemplo()  # Imprime 20 'vinte e uma' vezes
```

</details>
<details>
    <summary>Exemplos Práticos Detalhados</summary>

Exemplo 1: Escopo Local vs Global

```python

# Variável global

titulo = "Programa Principal"

funcao cumprimento():
    # Variável local
    nome = "João"
    imprime(titulo)      # ✅ Acesso global
    imprime(nome)        # ✅  local

funcao despedida():
    # Variável local diferente
    nome = "Maria"
    imprime(titulo)      # ✅  global
    imprime(nome)        # ✅  local (de despedida)
    # imprime(nome)      # ❌ Se tentasse acessar nome de cumprimento: ERRO

cumprimento()   # Programa Principal / João
despedida()     # Programa Principal / Maria
```
Exemplo 2: Shadowing (Obscurecimento)

```python
variavel = "Global"

funcao funcao():
    # Esta variável local "esconde" a global
    variavel = "Local"
    imprime(variavel)  # ✅ Imprime "Local"

funcao()                # Local
imprime(variavel)         # ✅ Global (não foi alterada)
```

Exemplo 3: Acessando Variáveis Globais Dentro de Função

```python
contador = 0

funcao incrementar():
    contador += 1
    imprime(f"Contador: {contador}")

incrementar()  # Contador: 1
incrementar()  # Contador: 2
imprime(contador)  # 2
```

## Regra de Ouro: LEGB
Em pseudoscript, a ordem de acesso a variáveis é (de dentro para fora):

- Local - Função atual
- Enclosing - Funções externas
- Global - Módulo inteiro


## Boas Práticas
|✅ Faça| ❌ Evite|
|-------|----------|
|Use variáveis locais sempre que possível |Variáveis globais desnecessárias|
|Declare global explicitamente se precisar Misturar escopos|-|
|Use nomes descritivos |Shadowing (nomes iguais em escopos diferentes)|
|Mantenha escopos pequenos e claros |Escopos muito grandes e complexos|

### Por Que É Importante?

- ✅ Evita conflitos de nomes
- ✅ Organiza o código
- ✅ Facilita manutenção
- ✅ Economiza memória (variáveis locais são destruídas)
- ✅ Evita efeitos colaterais inesperados

</details>

<details>
    <summary>Importação de Módulos</summary>

```python
importar NOME_DO_FICHEIRO  # Importa tudo o que está no ficheiro
importar NOME_DO_FICHEIRO como X  # Importa e renomeia como X
```

</details>



```python

## Tipos de Dados

```python
idade = 25                # Inteiro
altura = 1.75             # Float (Valores Dacimais)
primeiraLetra = "a"       # Char (caractere)
nome = "João"             # Texto (O Texto é considerado uma lista de caracteres [char])
isEstudante = verdadeiro  # Booleano
resultado = null          # Nulo (ausência de valor)
```

## Operadores Lógicos

O PseudoScript permite o uso de operadores lógicos simples para criar expressões condicionais e controlar o fluxo do programa.

**NOTA**: Uma comparação tem SEMPRE como seu resultado um valor booleano

### Operadores de Comparação

```python
a == b   # Igual a
a != b   # Diferente de
a > b    # Maior que
a < b    # Menor que
a >= b   # Maior ou igual a
a <= b   # Menor ou igual a

# Exemplos:
numero1 = 3
numero2 = 5

imprime(numero1==numero2) # Falso
imprime(numero1>numero2)  # Falso
imprime(numero1<numero2)  # Verdadeiro
```

### Operadores Lógicos

Os operadores lógicos ajudam a juntar (de forma inclusiva ou exclusica) várias comparações. Assim, podemos cobrir lógicas como `Isto E aquilo` ou `Aquilo OU o outro`

```python
verdadeiro E falso   # Operador E (ambas as condições têm de ser verdadeiras)
verdadeiro OU falso  # Operador OU (uma das condições tem de ser verdadeira)
NÃO verdadeiro       # Operador NÃO (inversão do valor booleano)

# Exemplos:
imprime(verdadeiro E Falso) # Falso. Neste caso ambas as condições têm de ser 'verdadeiro' (Inclusivo)
imprime(verdadeiro OU Falso) # Verdadeiro. Neste caso Basta uma condição ser verdadeira para o seu resultado final ser VERDADEIRO (Exclusivo)
imprime(NAO Verdadeiro) # Falso. Neste caso pretende-se 'inverter' uma condição
```

### Operador de Contenção

```python
elemento EM lista  # Verifica se o elemento está na lista

# Exemplos:
lista = [1,2,3]
numero = 4
imprime(numero EM lista) # Falso. Pois o 4 não está contido na lista 
```

#### Exemplo de Uso

```python
# Operadores Lógicos com E, OU e NÃO
se idade >= 18 E isEstudante == verdadeiro:
    imprime("Maior de idade e estudante.")
senao se idade < 18 OU isEstudante == falso:
    imprime("Menor de idade ou não é estudante.")
senao:
    imprime("Maior de idade.")

# Operador EM
lista = [1, 2, 3, 4, 5]
se 3 EM lista:
    imprime("O número 3 está na lista.")
senao:
    imprime("O número 3 não está na lista.")

# Operador NÃO
se NÃO isEstudante:
    imprime("Não é estudante.")
```

## Entrada e Saída

```python
entrada("Digite o seu nome: ", nome)
segredo("Palavra-passe: ", password)  # Entrada "segredo" oculta o valor digitado
imprime("Olá, {nome}")
```

## Controlo de Fluxo

### Condicionais

Blocos condicionais são estruturas de controlo de fluxo que permitem que um programa tome decisões e execute diferentes escopos de código com base em condições específicas.
Um bloco condicional avalia uma expressão (que resulta **SEMPRE** em verdadeiro ou falso) e executa diferentes ações dependendo do resultado da sua avaliação.

```python
se [Condição]:
    façaAlgo()
senao [outra Condição]:
    façaAlgoDiferente()
senao:
    façaOutraCoisa()
```

### Iterações (Loops)

Iterações (também chamadas de loops ou laços) são estruturas de controlo de fluxo que permitem repetir um escopo de código múltiplas vezes, sem precisar reescrevê-las.
Uma iteração executa um conjunto de instruções repetidamente enquanto uma condição for verdadeira, ou para cada elemento de uma lista.

```python
cada elemento em lista:
    processeElemento(elemento)
    continua()  # Passa para o próximo ciclo

enquanto [condição]:
    façaAlgo()
    quebra()  # Sai do ciclo
```

### Funções e Listas

```python
# Função
funcao somar(a, b):
    resultado = a + b
    retorne resultado

resultado = somar(2,2) # 4


#Listas
minhaLista = [1, 2, 3, 4, 5]
primeiroElemento = minhaLista[0]
sublista = minhaLista[0:1]  # [1, 2]
ultimoElemento = minhaLista[-1] # 5
sublistaAContarDoFim = minhaLista[1:-1] # [2,3,4]
tamanhoDaLista = tamanho(minhaLista)  # Tamanho da lista
minhaLista.adicionar(6)  # Adicionar elemento
```

## Dicionários (Mapas)

```python
carro = ('marca' -> 'Opel', 'modelo' -> 'Astra')

# Aceder a valores
imprime(carro.marca)
imprime(carro['modelo'])

# Operações com Dicionários

# Adicionar uma nova chave-valor
carro['ano'] = 2020

# Iterar chaves e valores
cada chave, valor em carro:
    imprime("Chave: {chave}, Valor: {valor}")

# Iterar apenas as chaves
cada chave em carro.chaves():
    imprime(chave)

# Iterar apenas os valores
cada valor em carro.valores():
    imprime(valor)


```

## Orientação a Objetos (OOP)

### funcaoinição de Classes

```python
modelo Pessoa:
    construtor(nome, idade):
        Pessoa.nome = nome
        Pessoa.idade = idade

    funcao apresentar():
        retorne "Olá, o meu nome é {Pessoa.nome} e tenho {Pessoa.idade} anos."
```

### Criação de Objetos e Herança

```python
modelo Estudante extende Pessoa:
    construtor(nome, idade, curso):
        Estudante.nome = nome
        Estudante.idade = idade
        Estudante.curso = curso

    funcao apresentarCurso():
        retorne "Estou no curso de {Estudante.curso}"

# Criar instância e usar métodos
alice = Estudante("Alice", 22, "Informática")
imprime(alice.apresentar())  # Herança de Pessoa
imprime(alice.apresentarCurso())  # Método de Estudante
```

## Métodos Auxiliares

```python
aleatorio() # gera um número aleatório
aleatorio(1,10) #gera um número aleatório entre 1 e 10
```

## Exemplos de Algoritmos

```python
funcao somaDosPares(n):
    resultado = 0
    cada i em lista(1, n + 1):
        se i % 2 == 0: # o simbolo % calcula o resto da divisão
            resultado = resultado + i
    retorne resultado

funcao fatorial(n):
    se n == 0:
        retorne 1
    senao:
        retorne n * fatorial(n - 1)
```

# Como Executar um Programa em PseudoScript

- Para executar um programa, crie um ficheiro com nome descritivo em letras maiúsculas como INICIO.pseudoscript.

```python
# INICIO.pseudoscript
importar src/programa como MeuPrograma

app = MeuPrograma.Programa()
app.start()
```

# Pontos Principais

Sintaxe Simplificada: Sintaxe minimalista para facilitar o aprendizado.
Tipagem Dinâmica: As variáveis podem ter o seu tipo modificado conforme o contexto.
Estruturas de Dados Simples: Listas, dicionários e funções básicas.
Orientação a Objetos: Conceitos básicos de OOP, com herança e métodos.

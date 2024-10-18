# PseudoScript: Uma Linguagem de Programação para quem quer aprender lógica

O PseudoScript é projetado para ser um ponto de partida para iniciantes. Após dominar os conceitos básicos, os aspirantes podem fazer uma transição mais fácil para a programação real em JavaScript ou Python. Ele fornece uma base sólida em lógica, estruturas de controlo e resolução de problemas sem sobrecarregar os iniciantes com uma sintaxe complexa.

## Importação de Módulos
```python
importar NOME_DO_FICHEIRO  # Importa tudo o que está no ficheiro
importar NOME_DO_FICHEIRO como X  # Importa e renomeia como X
```
## Tipos de Dados
```python
idade = 25                # Inteiro
altura = 1.75             # Float
primeiraLetra = "a"       # Char
nome = "João"             # Texto
isEstudante = verdadeiro  # Booleano
resultado = null          # Nulo (ausência de valor)
```
## Operadores Lógicos
O PseudoScript permite o uso de operadores lógicos simples para criar expressões condicionais e controlar o fluxo do programa.

### Operadores de Comparação
```python
a == b   # Igual a
a != b   # Diferente de
a > b    # Maior que
a < b    # Menor que
a >= b   # Maior ou igual a
a <= b   # Menor ou igual a
```
### Operadores Lógicos
```python
verdadeiro E falso   # Operador E (ambas as condições têm de ser verdadeiras)
verdadeiro OU falso  # Operador OU (uma das condições tem de ser verdadeira)
NÃO verdadeiro       # Operador NÃO (inversão do valor booleano)
```
### Operador de Contenção
```python
elemento EM lista  # Verifica se o elemento está na lista
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
```python
se [Condição]:
    façaAlgo()
senao [outra Condição]:
    façaAlgoDiferente()
senao:
    façaOutraCoisa()
```
### Iterações (Loops)
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
### Definição de Classes
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


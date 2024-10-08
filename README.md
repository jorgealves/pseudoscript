# pseudoscript
PseudoScript: Uma Linguagem de Programação para quem quer aprender lógica

O PseudoScript é projetado para ser um ponto de partida para iniciantes. Após dominar os conceitos base, os aspirantes podem fazer uma transição mais fácil para a programação real em JavaScript ou Python. Ele fornece uma base sólida em lógica, estruturas de controlo e resolução de problemas sem sobrecarregar os iniciantes com uma sintaxe complexa.

```python

# importar ficheiros(pacotes/Módulos)
importar NOME_DO_FICHEIRO # importa tudo o que esteja dentro de um ficheiro
importar NOME_DO_FICHEIRO como X # Importa tudo e considera como X
# NOTA: Não precisa de adicionar a extensão do ficheiro.

# Variáveis são de tipagem dinâmica
nomeDaVariavel = "Olá, Mundo!"

# Entrada e Saída
entrada("Diga seu nome: ", nome)
segredo("Password: ", password) # tem o mesmo propósito de 'entrada' mas ao escrever o utilizador não vê os caracteres (*******)
imprime("Olá, " + nome)

aleatorio() # gerar um número aleatório
crash("Mensagem de erro que resultou um 'crash' do programa") # Esta função serve para reportar erros aplicacionais que originam no encerramento do programa

# Declarações Condicionais
se [Condição]:
    # A indentação indica um bloco
    façaAlgo()
senao [outra Condição]:
    façaAlgoDiferente()
senao:
    façaOutraCoisa()

# Iterações (Loops)
cada elemento em lista:
    processeElemento(elemento)
    continua() # Passa para o próximo ciclo

enquanto [condição]:
    façaAlgo()
    quebra() # sai do ciclo

# Funções
funcao somar(a, b):
    resultado = a + b
    retorne resultado

# Listas
minhaLista = [1, 2, 3, 4, 5]
primeiroElemento = minhaLista[0]
sublista = minhaLista[0:1] # [1,2]
sublista2 = minhaLista[::3] # [1,2,3,4]
subLista3 = minhalista[::-1] # [1,2,3,4]
sublista4 = minhaLista[2::] # [3,4,5]
minhaLista[2] = 42
tamanhoDaLista = tamanho(minhaLista) # ou minhaLista.tamanho()
minhaLista.adicionar(1) # [1,2,3,4,5,1]


# Mapas / Dicionario
#        Chave    Valor
#          |       |
#          v       v
carro = ('marca'->'opel', 'modelo'->'astra')
# Aceder a um valor através da sua chave
imprime(carro.marca)
imprime(carro['modelo'])

# iterar dicionario
notas = ('Joao'-> 10, 'Joana' -> 12)
cada chave, valor em notas
    imprime('o aluno {chave} tem uma nota de {valor}')

# iterar apenas as chaves
cada chave em notas.chaves():
    imprime(chave)

# iterar apenas os valores:
cada valor em chave.valores():
    imprime(valor)


# Orientação a Objetos (OOP)
# Definição de Classe
modelo Pessoa:
    construtor(nome, idade):
        Pessoa.nome = nome
        Pessoa.idade = idade

    funcao apresentar():
        retorne "Olá, meu nome é {Pessoa.nome} e tenho {Pessoa.idade} anos."

# Criação de Instância de Objeto
alice= Pessoa("Alice", 30)

# Chamada Método do Objeto
imprime(alice.apresentar())

# Comentários
# Este é um comentário de uma linha

/*
Este é um
comentário de
múltiplas linhas
*/

# Exemplo: Encontrando a soma dos números pares até n
funcao somaDosPares(n):
    resultado = 0
    cada i em lista(1, n + 1):
        se i % 2 == 0:
            resultado = resultado + i
    retorne resultado

# Exemplo: Fatorial
função fatorial(n):
    se n == 0:
        retorne 1
    senao:
        retorne n * fatorial(n - 1)

```

## Como correr um programa em pseudoscript
Para correr um programa em pseudoscript apenas temos de considerar um ficheiro
com o nome em maiúsculas (ex. MAIN ou INICIO ou ENTRYPOINT). Recomenda-se que o
nome do ficheiro seja elucidativo de que é neste ficheiro que devemos iniciar o 
nosso programa.

Depois devemos colocar nesse ficeiro todo o codigo necessário para correr o 
programa.

```python
# programa.pseudoscript

modelo Programa:
    
    funcao start():
        imprime('Olá Mundo!')

```

```python
# INICIO.pseudoscript

importar src/programa como MeuPrograma

app = MeuPrograma.Programa()
app.start()

```
## Principais Pontos:

- Sintaxe Simplificada: O PseudoScript utiliza uma sintaxe simples com poucos símbolos e recuo. Ele emprega construções amigáveis para humanos como se, para, enquanto e função.
- Tipagem Dinâmica: As variáveis são de tipagem dinâmica, facilitando o trabalho para iniciantes.
- Entrada e Saída Simples: Entrada e saída são tratadas com comandos simples entrada e saída.
- Comentários: O PseudoScript permite comentários de uma linha e de várias linhas para explicar o código.
- Estruturas de Dados Básicas: Ele introduz conceitos básicos de listas (arrays) e funções.
- Exemplos: Inclui funções de exemplo para ilustrar tarefas de programação comuns.

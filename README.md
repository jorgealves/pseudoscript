# pseudoscript
PseudoScript: Uma Linguagem de Programação para quem quer aprender lógica

O PseudoScript é projetado para ser um ponto de partida para iniciantes. Após dominar seus conceitos, os estudantes podem fazer uma transição mais fácil para a programação real em JavaScript ou Python. Ele fornece uma base sólida em lógica, estruturas de controle e resolução de problemas sem sobrecarregar os iniciantes com uma sintaxe complexa.

```js
# Variáveis são de tipagem dinâmica
nomeDaVariavel = "Olá, Mundo!"

# Entrada e Saída
entrada("Diga seu nome: ", nome)
imprime("Olá, " + nome)

# Declarações Condicionais
se [Condição]:
    # A indentação indica um bloco
    façaAlgo()
senão [outra Condição]:
    façaAlgoDiferente()
senão:
    façaOutraCoisa()

# Iterações (Loops)
cada elemento em lista:
    processeElemento(elemento)

enquanto [condição]:
    façaAlgo()

# Funções
função somar(a, b):
    resultado = a + b
    retorne resultado

# Listas
minhaLista = [1, 2, 3, 4, 5]
primeiroElemento = minhaLista[0]
minhaLista[2] = 42
tamanhoDaLista = tamanho(minhaLista) # ou minhaLista.tamanho()

# Orientação a Objetos (OOP)
# Definição de Classe
classe Pessoa:
    construtor(nome, idade):
        my.nome = nome
        my.idade = idade

    função apresentar():
        retorne "Olá, meu nome é {my.nome} e tenho {my.idade} anos."

# Criação de Instância de Objeto
alice = Pessoa("Alice", 30)

# Chamada Método do Objeto
imprime(alice.apresentar()

# Comentários
# Este é um comentário de uma linha

/*
Este é um
comentário de
múltiplas linhas
*/

# Exemplo: Encontrando a soma dos números pares até n
função somaDosPares(n):
    resultado = 0
    cada i em lista(1, n + 1):
        se i % 2 == 0:
            resultado = resultado + i
    retorne resultado

# Exemplo: Fatorial
função fatorial(n):
    se n == 0:
        retorne 1
    senão:
        retorne n * fatorial(n - 1)
```
## Principais Pontos:

- Sintaxe Simplificada: O PseudoScript utiliza uma sintaxe simples com poucos símbolos e recuo. Ele emprega construções amigáveis para humanos como se, para, enquanto e função.
- Tipagem Dinâmica: As variáveis são de tipagem dinâmica, facilitando o trabalho para iniciantes.
- Entrada e Saída Simples: Entrada e saída são tratadas com comandos simples entrada e saída.
- Comentários: O PseudoScript permite comentários de uma linha e de várias linhas para explicar o código.
- Estruturas de Dados Básicas: Ele introduz conceitos básicos de listas (arrays) e funções.
- Exemplos: Inclui funções de exemplo para ilustrar tarefas de programação comuns.

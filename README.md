# PseudoScript: Uma Linguagem de Programação para quem quer aprender lógica

O PseudoScript é projetado para ser um ponto de partida para iniciantes. Após dominar os conceitos básicos, os aspirantes podem fazer uma transição mais fácil para a programação real em JavaScript ou Python. Ele fornece uma base sólida em lógica, estruturas de controlo e resolução de problemas sem sobrecarregar os iniciantes com uma sintaxe complexa.

<details>
    <summary>Escopo</summary>

Escopo é a região do programa onde uma variável, função ou constante pode ser acedida e utilizada. É como uma "zona de visibilidade" para elementos do código.
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

imprime(valor)  // ❌ ERRO: valor não está funcao
---
frase="Olá Mundo!"
cada letra em frase:
    imprime(letra) # ✅ Funciona
imprime(letra)  // ❌ ERRO: Letra não está neste escopo

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

    repeticao = 20
    enquanto repeticao >= 0:
        imprime(pontos)
        repeticao = repeticao + 1  # ✅ Acede 'pontos' da função

exemplo()  # Imprime 20 'vinte e uma' vezes
```

</details>



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

A importação de módulos é a forma recomendada de partilhar e reutilizar código em PseudoScript. 
Um módulo pode exportar funções, variáveis e tipos; ao importar um módulo, trazes essas exportações para o contexto atual, mantendo o código modular e fácil de manter. 
Tipicamente consegues:

- importar um módulo completo;
- importar só símbolos específicos (funções/constantes);
- renomear (alias) módulos para evitar conflitos.

```python
importar NOME_DO_FICHEIRO  # Importa tudo o que está no ficheiro
importar NOME_DO_FICHEIRO como X  # Importa e renomeia como X
```

</details>

<details>
    <summary>Tipos de Dados</summary>
    
São a base para representar informação em PseudoScript. 

Cada tipo define o formato dos valores, as operações válidas e frequentemente a forma como os valores são guardados em memória. 

A documentação abaixo explica os tipos primitivos e compostos mais comuns e dá exemplos de uso.

### Tipos primitivos comuns

- Inteiro (int): números sem parte decimal. Ex.: 0, 42, -7. Exemplo: `a = 10`
- Decimal / Real / ponto flutuante (float): números com casas decimais. Ex.: 3.14, -0.5 Exemplo: `pi = 3.14`
- Booleano (bool): verdadeiro ou falso — usado para condições. Exemplo: let ativo = true
- Texto / string (string): sequência de caracteres. Exemplo: let nome = "Ana"
- Nulo / indefinido (null / nil / undefined): representa ausência de valor. Exemplo: let resultado = null

```python
idade = 25                # Inteiro
altura = 1.75             # Float (Valores Dacimais)
primeiraLetra = "a"       # Char (caractere)
nome = "João"             # Texto (O Texto é considerado uma lista de caracteres [char])
isEstudante = verdadeiro  # Booleano
resultado = null          # Nulo (ausência de valor)
```

### Tipos compostos

- Lista / array: coleção ordenada de valores. Exemplo: `nums = [1, verdadeiro, 'olá']`
- Dicionário / mapa: coleção de pares chave–valor. Exemplo: `pessoa = ('nome' -> "João", 'idade' -> 30)`

```python
# Lista
notas = [15,16,16,17,17]

# Dicionário / Mapa
dicionario =(
    'nome' -> 'John',
    'apelido' -> 'Doe',
    'idade' -> 27
)
```
</details>

<details>
    <summary>Operadores Lógicos</summary>

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

O operador de contenção testa se um elemento faz parte de uma coleção (lista, mapa — chaves ou valores) ou se uma substring está presente numa string, produzindo um booleano.

```python
elemento EM lista  # Verifica se o elemento está na lista

# Exemplos:
lista = [1,2,3]
numero = 4
imprime(numero EM lista) # Falso. Pois o 4 não está contido na lista

imprime('Tóquio' EM 'Gosto de ir a Tóquio')  # Verdadeiro
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
</details>

<details>
    <summary>Entrada e Saída</summary>
    
- Entrada: obter dados de fontes externas — por exemplo teclado (prompt), ficheiros ou argumentos.
```python
entrada("Qual o seu nome? ", nome) # exporta o que o utilizador insere para a variavel 'nome'
segredo("Password: ", password) # faz o mesmo que o 'entrada', porém oculta o que o utilizador insere (com '*****')
```
- Saída: mostrar resultados ao utilizador.
```python
imprime("Isto é para mostrar ao utilizador")
```

## Comportamento:
- Leitura do teclado normalmente retorna uma string;
- Impressão converte valores para texto e escreve no ecrã ou num ficheiro.

## Interpolação de strings com `{…}`

- Sintaxe: usar `{expressão}` dentro de uma string para inserir o valor resultante da expressão nessa posição.
- Avalia a expressão e a converte para texto automaticamente.
- Permite inserir variáveis, chamadas de função ou operações (ex.: {idade + 1}).
- Vantagem: código mais limpo e legível comparado com concatenação manual.

Exemplos:

```python
# Leitura do teclado (retorna string)
entrada("Qual é o teu nome?", nome)
entrada("Qual a tua idade?", idade)

# Saída com interpolação simples
imprime("Olá, {nome}! Tens {idade} anos.")

# Interpolação com expressão
imprime("No próximo ano terás {idade + 1} anos.")

# Escape de chaves (para mostrar { } literalmente)
imprime("Usa {expressao} para interpolação; exemplo: {idade}")

entrada("Digite o seu nome: ", nome)
segredo("Palavra-passe: ", password)  # Entrada "segredo" oculta o valor digitado
imprime("Olá, {nome}")
```
</details>
<details>
    <summary>Controlo de Fluxo</summary>

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
<details>
    <summary>Funções</summary>
</details>
São unidades independentes de lógica que recebem zero ou mais argumentos, executam operações e opcionalmente retornam um valor. 

São a principal forma de modularizar programas e reutilizar código.

Declaração e chamada:

```python
# Definição com retorno
funcao soma(a, b):
  retorna a + b

r = soma(2, 3)   # r = 5

# Definição sem retorno explícito (efeito/printing)
funcao cumprimenta(nome) {
  imprime("Olá, {nome}!")
}
cumprimenta("Ana")
```

Conceitos importantes

- Parâmetros e argumentos: parâmetros são nomes na definição; argumentos são os valores passados.
- Retorno: uma função pode usar `retorna` para devolver um valor;
- Escopo: variáveis definidas dentro da função são locais e não visíveis fora dela.

Recursão: funções podem chamar a si mesmas para resolver problemas divisíveis.

Exemplos avançados 
```python
# Recursão: fatorial
funcao fatorial(n):
  se n <= 1:
    retorna 1
  retorna n * fatorial(n - 1)
```

### Boas práticas rápidas

- Dá nomes descritivos às funções (verbo + complemento): ex.: calcular_imposto, ler_ficheiro.
- Mantém funções pequenas e com responsabilidade única.
- Documenta parâmetros e valores de retorno.
- Evita efeitos colaterais inesperados; valida entradas antes de operar.

```python
# Função
funcao somar(a, b):
    resultado = a + b
    retorne resultado

resultado = somar(2,2) # 4
```
</details>
<details>
    <summary>Listas</summary>

- Indexação: `lista[i]` dá o i-ésimo elemento (i começa em 0). índice -1 é o último.
- Slicing / sublistas: `lista[start:end]` inclui elementos desde start até end-1 (fim exclusivo).
    - Slices produzem normalmente uma nova lista (cópia).
- Para verificar pertença, usa `em` (ex.: `3 em lista`).

Explicação linha a linha (com correções)

```python
# Listas
minhaLista = [1, 2, 3, 4, 5]
primeiroElemento = minhaLista[0]       # 1 (índice 0)
sublista = minhaLista[1:2]             # [1, 2,3]  <-- corrigido: end é inclusivo
ultimoElemento = minhaLista[-1]        # 5 (índice -1)
sublistaAContarDoFim = minhaLista[1:-1]# [2, 3, 4]  (start=1, end=-1 => até o penúltimo)
tamanhoDaLista = tamanho(minhaLista)   # 5 (existem 5 elementos no array)
minhaLista.adicionar(6)                # [1,2,3,4,5,6]
```
### Regras importantes sobre slices (sublistas)

- `start` é incluído, `end` é incluido. Ex.: lista[0:2] → elementos 0, 1 e 2.
- Se omites `start`: `lista[:end]` começa em 0. Se omites `end`: `lista[start:]` vai até ao fim.
- Se omites ambos: `lista[:]` faz uma cópia da lista inteira. O mesmo que `lista`
- Índices fora de intervalo causam erro.
- Slices criam uma nova lista (mutações na sublista não alteram a original).
  
#### Exemplos adicionais úteis

```python
minhaLista = [1,2,3,4,5]
imprime(minhaLista[:2])    # [1, 2]  (do início até índice 1)
imprime(minhaLista[2:])    # [3, 4, 5] (do índice 2 até ao fim)
sub = minhaLista[0:3]
sub[0] = 99                # altera só a sublista; não altera a original
```

### Boas práticas rápidas

- Usa slice para extrair partes de uma lista sem escrever loops.
- Documenta se funções aceitam/pedem sublistas ou conjuntos (comportamento esperado).
  
</details>
<details>
    <summary>Dicionários/Mapas</summary>
- Estruturas chave→valor: cada chave associa-se a um único valor. Exemplos de uso: representar um registo de pessoa, contador por categoria, cache, ou JSON.

Criação e acesso:

```python
# criar
              Chave     Valor
                |        |
                v        v
pessoa = ("nome"> "Ana", "idade"> 30}
vazio = ()

# acesso
nome = pessoa["nome"]      # "Ana". Também podemos aceder, se soubermos a sua chave, `pessoa.nome`

# inserir / atualizar
pessoa["idade"] = 31
pessoa["cidade"] = "Porto"

# Métodos e operações comuns:

em: verificar se uma chave existe (ex.: "nome" em pessoa).
chaves(), valores(): iterar chaves, valores.
tamanho(): obter número de items.
```

Exemplos de iteração e aninhamento

```python
# iterar chaves
cada chave em pessoa.chaves():
  imprime(chave)

# iterar pares
cada chave, valor em pessoa:
  print("{chave}: {valor}")

# mapas aninhados
config = ("db"-> ("host"-> "localhost", "port"-> 5432))
host = config["db"]["host"]
```

## Boas práticas

- As chaves são SEMPRE únicas.
- Usa comparações explícitas para evitar erros quando a chave não existir.
- Documenta formato esperado (quais chaves existem e tipos dos valores).
- Evita mutar um mapa enquanto o iteras; se precisares, itera sobre uma cópia das chaves.

### Armadilha comum

- Confundir verificar existência de chave com verificar valor truthy (chave pode existir com valor null/false).

### Pequenos exemplos úteis

```python
# contador usando mapa
contadores = ()
cada item em lista:
  se item em contadores:
    contadores[item] = contadores[item] + 1
    continua() # Passa para o próximo ciclo
  contadores[item] = 1

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
</details>

<details>
    <summary>Modelos</summary>

Modelos são o mecanismo da linguagem para definir tipos compostos com atributos (campos) e comportamentos (métodos). 

Um modelo descreve a estrutura e as operações que as suas instâncias (objetos) terão.

## Quando usar modelos
- Para agrupar dados relacionados e operações sobre esses dados.
- Para representar entidades do domínio (pessoas, contas, formas, etc.).
- Para reutilizar e estender comportamentos através de herança.

## Sintaxe básica

### Definição de um modelo:
```
modelo NomeDoModelo:
    construtor(param1, param2, ...):
        NomeDoModelo.campo1 = param1
        NomeDoModelo.campo2 = param2
    funcao nomeMetodo():
        retorne "algum valor"
```
- `modelo` inicia a definição.
- `construtor(...)` é invocado quando se cria uma instância; deve inicializar os campos.
- Os campos são atribuídos usando a notação `NomeDoModelo.campo`.
- `funcao` define métodos que podem aceder aos campos do modelo com `NomeDoModelo.campo`.

### Instanciação e uso:
```
instancia = NomeDoModelo(arg1, arg2)
imprime(instancia.metodo())
```
## Exemplos explicados

1) Modelo simples — Pessoa
```
modelo Pessoa:
    construtor(nome, idade):
        Pessoa.nome = nome
        Pessoa.idade = idade

    funcao apresentar():
        retorne "Olá, o meu nome é {Pessoa.nome} e tenho {Pessoa.idade} anos."
```
- O construtor cria os campos `nome` e `idade`.
- O método `apresentar` usa esses campos para devolver uma string.

Uso:
```
alice = Pessoa("Alice", 30)
imprime(alice.apresentar())

# Saída esperada: Olá, o meu nome é Alice e tenho 30 anos.
```

## Boas práticas
- Inicialize todos os campos necessários no `construtor`.
- Use nomes de campos consistentes para evitar confusão entre pai e filho.
- Quando estender um modelo, confirme se precisa inicializar campos do pai no construtor do filho.
- Separe responsabilidades: mantenha métodos curtos e focados numa única ação.

## Armadilhas comuns
- Esquecer de definir um campo no construtor e depois tentar usá-lo em métodos.
- Contar com inicialização automática do construtor do pai quando a linguagem não a faz.
- Usar nomes de campo idênticos sem intenção, levando a sobrescritas acidentais.

## Resumo rápido
- Modelos encapsulam dados e comportamentos.
- `construtor(...)` cria e inicializa campos.
- `funcao` define métodos que usam `NomeDoModelo.campo`.
- `extende` permite herança; trate explicitamente a inicialização de campos herdados quando necessário.

```python
modelo Pessoa:
    construtor(nome, idade):
        Pessoa.nome = nome
        Pessoa.idade = idade

    funcao apresentar():
        retorne "Olá, o meu nome é {Pessoa.nome} e tenho {Pessoa.idade} anos."
```


</details> 
<details>
    <summary>Métodos Auxiliares</summary>

```python
aleatorio() # gera um número aleatório
aleatorio(1,10) #gera um número aleatório entre 1 e 10
```
</details>

<details>
    <summary>Como Executar um Programa em PseudoScript</summary>

- Para executar um programa, crie um ficheiro com nome descritivo em letras maiúsculas como INICIO.pseudoscript.

```python
# INICIO.pseudoscript
importar src/programa como MeuPrograma

app = MeuPrograma.Programa()
app.start()
```
</details>

# Pontos Principais

- Sintaxe Simplificada: Sintaxe minimalista para facilitar o aprendizado.
- Tipagem Dinâmica: As variáveis podem ter o seu tipo modificado conforme o contexto.
- Estruturas de Dados Simples: Listas, dicionários e funções básicas.
- Orientação a Objetos: Conceitos básicos de OOP, com herança e métodos.

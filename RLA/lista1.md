# UNIFOR
**Nome**: Edward Stewart <br>
**Disciplina**: Raciocínio lógico algorítmico

## Lista de exercícios 01

### Exercício 01 (1 ponto)
Represente, em fluxograma e pseudocódigo, um algoritmo para determinar se um número inteiro e positivo é par ou impar.

#### Fluxograma (0,25 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um número:}}
B --> C[\numero\]
C --> D{numero >= 0}
D --FALSE--> E[O número não é positivo!]
D --TRUE--> F[resto = numero % 2]
E --> Z([FIM])
F --> G{resto == 0}
G --FALSE--> H{{O número é impar!}}
G --TRUE--> I{{O número é par!}}
H --> Z
I --> Z
```

#### Pseudocódigo (0,5 ponto)
```
1  ALGORTIMO verifica_par_impar
2  DECLARE numero, resto: INTEIRO
3  ESCREVA "Digite um número: "
4  INICIO
4  LEIA numero
5  SE numero >= 0 ENTAO                  // verifica se o inteiro é positivo
6    resto = numero % 2                 // calcula o resto da divisão por 2
7    SE resto == 0 ENTAO                // verifica se o resto é igual a zero
8      ESCREVA "O número é par!"
9    SENAO
10     ESCREVA "O número é impar!"
11   FIM_SE
11  SENAO                                // caso inteiro for negativo (condição linha 5)
12    ESCREVA "O número deve ser postivo!"
13  FIM_SE
13 FIM
```

#### Teste de mesa (0,25 ponto)
| numero | numero >= 0 | resto | resto == 0 | Saída |
| -- | -- | -- | -- | -- | 
| -1 | F |   |   | "O número deve ser postivo!" |
| 0  | V | 0 | V | "O número é par!" |
| 13 | V | 1 | F | "O número é impar!" |
| 30 | V | 0 | V | "O número é par!" |

## Exercício 02 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular o novo salário de um funcionário. 
Sabe-se que os funcionários que recebem atualmente salário de até R$ 500 terão aumento de 20%; os demais terão aumento de 10%.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INÍCIO]) --> B{Digite o salário atual do funcionário} 
B --> C[\salario_atual\] 
C --> D{salario_atual <= 500} 
D --TRUE--> E[Novo_salario = salario_atual * 1.2] 
D --FALSE--> F[Novo_salario = salario_atual * 1.1] 
E --> G([FIM]) 
F --> G([FIM]) 
G --> H{Exibir Novo_salario}
H --> I([FIM])
```

#### Pseudocódigo (1.0 ponto)

```
ALGORITMO calcular_novo_salario
INÍCIO 
DECLARE salario_atual, novo_salario NUMÉRICO 
ESCREVA "Digite o salário atual "
LEIA salario_atual 
SE salario_atual <= 500 ENTAO novo_salario = salario_atual * 1.20 
SENAO novo_salario = salario_atual * 1.10
FIM_SE 
ESCREVA "O novo salário do funcionário é: " novo_salario 
FIM
```

#### Teste de mesa (1.0 ponto)

| nome_coluna1 | nome_coluna2 | nome_coluna3 | nome_coluna4 | nome_coluna5 | 
|      --      |      --      |      --      |      --      |      --      | 
| Adicione     | espaço       | se quiser    |  alinhar     | as barras    |
| verticais,   | mas          | não é        | obrigatório. | Entendido ?  |

## Exercício 03 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo para calcular a média aritmética entre duas notas de um aluno e mostrar sua situação, que pode ser aprovado ou reprovado.

#### Fluxograma (1 ponto)

```mermaid
flowchart TD 
A([INÍCIO]) --> B{Digite a primeira nota} 
B --> C[\nota1\] 
C --> D{nota1 >= 0 e nota1 <= 10} 
D --TRUE--> E{Digite a segunda nota} 
E --TRUE--> F[\nota2\] 
F --> G{nota2 >= 0 e nota2 <= 10} 
G --TRUE--> H{media = nota1 + nota2, / 2} 
H --TRUE--> I{media >= 6} 
I --TRUE--> J{Exibir Aprovado}
J --> K([FIM])
I --FALSE--> L{Exibir Reprovado}
L --> K 
H --FALSE--> M{Exibir Notas inválidas} 
M --> K 
D --FALSE--> M 
C --FALSE--> M
```

#### Pseudocódigo (1 ponto)

```
ALGORITMO calcular_media 
INÍCIO
DECLARE nota1, nota2, media NUMÉRICO 
ESCREVA "Digite a primeira nota do aluno " 
LEIA nota1 
ESCREVA "Digite a segunda nota do aluno: " 
LEIA nota2  = (nota1 + nota2) / 2
SE media >= 6.0 ENTAO ESCREVA "Aluno aprovado!" 
SENAO
ESCREVA "Aluno reprovado!" 
 FIM_SE 
 FIM
```

#### Teste de mesa (1 ponto)

| nome_coluna1 | nome_coluna2 | nome_coluna3 | nome_coluna4 | nome_coluna5 | 
|      --      |      --      |      --      |      --      |      --      | 
| Adicione     | espaço       | se quiser    |  alinhar     | as barras    |
| verticais,   | mas          | não é        | obrigatório. | Entendido ?  |

## Exercício 04 (3 pontos)
Represente, em fluxograma e pseudocódigo, um algoritmo que, a partir da idade do candidato(a), determinar se pode ou não tirar a CNH. 
Caso não atender a restrição de idade, calcular quantos anos faltam para o candidato estar apto.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD 
A([INÍCIO]) --> B{Digite a idade do candidato} 
B --> C[\idade\] 
C --> D{idade >= 18} 
D --TRUE--> E{Exibir Candidato apto para tirar CNH} 
E --> F([FIM]) 
D --FALSE--> G{Exibir Candidato não apto para tirar CNH} 
G --> H{calcular anos que faltam} 
H --> I([FIM])
```

#### Pseudocódigo (1.0 ponto)

```
ALGORITMO verificar_cnh 
INÍCIO 
DECLARE idade, idade_minima, anos_faltando INTEIRO 
idade_minima = 18
ESCREVA "Digite a idade do candidato: " 
LEIA idade 
SE idade >= idade_minima 
ENTAO 
ESCREVA "O candidato pode tirar a CNH." 
SENAO anos_faltando = idade_minima - idade 
ESCREVA "Só poderá tirar a CNH após" anos_faltando "ano(s)"
FIM_SE 
FIM
```

#### Teste de mesa (1.0 ponto)

| nome_coluna1 | nome_coluna2 | nome_coluna3 | nome_coluna4 | nome_coluna5 | 
|      --      |      --      |      --      |      --      |      --      | 
| Adicione     | espaço       | se quiser    |  alinhar     | as barras    |
| verticais,   | mas          | não é        | obrigatório. | Entendido ?  |

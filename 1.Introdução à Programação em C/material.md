
# Introdução à Algoritmos e Programação em C

## 1. Hello World em C
O primeiro programa em qualquer linguagem geralmente é o "Hello World". Em C:

```c
#include <stdio.h>

int main() {
    // Imprime na tela
    printf("Hello World!\n");
    return 0;
}
```
**Explicação:**
- `#include <stdio.h>`: Biblioteca para operações de entrada/saída
- `int main()`: Função principal onde o programa inicia
- `printf()`: Função para imprimir texto na tela
- `\n`: Caractere especial para nova linha
- `return 0;`: Indica que o programa terminou com sucesso

## Como Compilar e Executar
1. Primeiro instale o MinGW no seu computador e um aplicativo para manipular texto (Recomendo o `VScode`)
   ```Link para Tutorial
   https://youtu.be/BKsdbwGEsDM?si=pwNm5UsvS5BlFBzM
   ```
1. Salve o código em um arquivo `.c` (ex: `programa.c`)
2. Abra o terminal e compile:
   ```bash
   gcc programa.c -o programa
   ```
3. Execute:
   ```bash
   ./programa
   ```

## 2. O que são Variáveis?
Variáveis são espaços na memória para armazenar dados. Devem ser declaradas antes do uso.

**Características:**
- Tem um **nome** único (identificador)
- Possuem um **tipo** de dados
- Podem ter seu valor alterado

**Exemplo em C:**
```c
int idade = 25;          // Inteiro
float altura = 1.75;     // Número decimal
char letra = 'A';        // Caractere
```

### Desafio 2.1
Declare variáveis para armazenar:
- Seu ano de nascimento
- A temperatura atual
- A primeira letra do seu sobrenome

### Desafio 2.2
Crie um programa que declare uma variável para cada tipo básico (int, float, char) e imprima seus valores.


## 3. Tipos de Dados Básicos
Principais tipos em C:

| Tipo    | Tamanho (bytes) | Descrição               | Exemplo      |
|---------|-----------------|-------------------------|--------------|
| int     | 4               | Números inteiros        | 42, -15      |
| float   | 4               | Números decimais        | 3.14, -0.5   |
| double  | 8               | Decimais com mais precisão | 9.8765     |
| char    | 1               | Caractere               | 'a', '$'     |

**Declaração:**
```c
int numero = 10;
double pi = 3.1415926535;
char simbolo = '#';
```

### Desafio 3.1
Descubra e imprima o tamanho em bytes de cada tipo usando `sizeof(float"Por Exemplo")`.

### Desafio 3.2
Crie um programa que mostre os valores máximo e mínimo que um `int` pode armazenar.


## 4. Entrada de Dados
Usamos a função `scanf()` para ler dados do usuário:

**Sintaxe:**
```c
scanf("%formatador", &variavel);
```

**Exemplo:**
```c
#include <stdio.h>

int main() {
    int idade;
    
    printf("Digite sua idade: ");
    scanf("%d", &idade);  // Lê um inteiro
    
    printf("Você tem %d anos.\n", idade);
    return 0;
}
```

**Formatadores comuns:**
- `%d` para int
- `%f` para float
- `%lf` para double
- `%c` para char

### Desafio 4.1
Crie um programa que peça ao usuário seu nome (apenas a primeira letra) e idade, depois os imprima.

### Desafio 4.2
Faça um conversor de Celsius para Fahrenheit. Peça a temperatura em Celsius e mostre o equivalente em Fahrenheit (F = C × 9/5 + 32).


## 5. Operações com Dados
Operadores aritméticos básicos:

| Operador | Descrição       | Exemplo   | Resultado |
|----------|-----------------|-----------|-----------|
| +        | Adição          | 5 + 3     | 8         |
| -        | Subtração       | 10 - 4    | 6         |
| *        | Multiplicação   | 6 * 7     | 42        |
| /        | Divisão         | 15 / 2    | 7 (int)   |
| %        | Módulo (resto)  | 15 % 2    | 1         |

**Exemplo em C:**
```c
#include <stdio.h>

int main() {
    int a = 15, b = 4;
    
    printf("Soma: %d\n", a + b);        // 19
    printf("Subtração: %d\n", a - b);   // 11
    printf("Multiplicação: %d\n", a * b);// 60
    printf("Divisão inteira: %d\n", a / b); // 3
    printf("Resto: %d\n", a % b);       // 3
    
    float divisaoReal = (float)a / b;
    printf("Divisão real: %.2f\n", divisaoReal); // 3.75
    
    return 0;
}
```

### Desafio 5.1
Crie uma calculadora simples que peça dois números e mostre:
- A soma
- A diferença (do maior pelo menor)
- O produto
- A divisão real

### Desafio 5.2
Faça um programa que converta segundos em horas, minutos e segundos (ex: 4000 segundos = 1h 6min 40s).


**Importante:**
- Divisão entre inteiros resulta em inteiro
  ```Exemplo
  float a = 5 / 2 // 2.000000
  ```
- Para divisão real, converter pelo menos um operando para float/double
  ```Exemplo
  float a = 5.0 / 2 // 2.500000
  ```
- Ordem de precedência: () → * / % → + -
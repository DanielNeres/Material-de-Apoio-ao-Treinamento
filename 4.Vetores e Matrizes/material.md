## Vetores e Matrizes
### 1. Vetores (Arrays): Uma Coleção Organizada

Imagine que você precisa guardar as notas de todos os alunos de uma turma. Em vez de criar uma variável para cada aluno (nota1, nota2, nota3...), seria muito mais prático ter um único "lugar" capaz de armazenar todas essas notas de forma organizada. É exatamente isso que um **vetor** (também conhecido como *array*) nos permite fazer.

**Definição:** Um vetor é uma estrutura de dados que armazena uma sequência de elementos do **mesmo tipo** (inteiros, caracteres, números decimais, etc.) em posições de memória contíguas (lado a lado). Cada elemento dentro do vetor é identificado por um **índice**, que funciona como um "endereço" para acessar aquele elemento específico.

**Analogia:** Pense em um prédio com vários apartamentos. O prédio inteiro é o vetor, e cada apartamento é um elemento. O número do apartamento seria o índice que nos permite encontrar um apartamento específico.

**Declaração de um Vetor em C:**

Para criar um vetor em C, precisamos declarar seu tipo, nome e tamanho (o número máximo de elementos que ele pode armazenar). A sintaxe geral é:

```c
tipo nome_do_vetor[tamanho];
```

**Exemplos:**

* Um vetor para armazenar 5 números inteiros:
    ```c
    int notas[5];
    ```
    Aqui, `int` indica que o vetor armazenará números inteiros, `notas` é o nome do nosso vetor e `[5]` define que ele pode guardar até 5 elementos. Os índices deste vetor vão de 0 a 4 (sempre começando em 0).

* Um vetor para armazenar 10 caracteres:
    ```c
    char letras[10];
    ```
    Este vetor pode armazenar até 10 caracteres individuais.

**Acessando Elementos do Vetor:**

Para acessar um elemento específico do vetor, usamos o nome do vetor seguido do índice do elemento entre colchetes. Lembre-se que a indexação sempre começa em 0.

```c
#include <stdio.h>

int main() {
    int numeros[3]; // Declara um vetor de 3 inteiros

    numeros[0] = 10; // Atribui o valor 10 ao primeiro elemento (índice 0)
    numeros[1] = 25; // Atribui o valor 25 ao segundo elemento (índice 1)
    numeros[2] = 5;  // Atribui o valor 5 ao terceiro elemento (índice 2)

    printf("O primeiro elemento é: %d\n", numeros[0]); // Saída: O primeiro elemento é: 10
    printf("O segundo elemento é: %d\n", numeros[1]);  // Saída: O segundo elemento é: 25
    printf("O terceiro elemento é: %d\n", numeros[2]); // Saída: O terceiro elemento é: 5

    return 0;
}
```

**Inicialização de Vetores:**

Podemos inicializar os elementos de um vetor no momento da declaração:

```c
int valores[] = {1, 5, 12, 8, 3}; // O tamanho é inferido como 5
char vogais[5] = {'a', 'e', 'i', 'o', 'u'};
float temperaturas[3] = {25.5, 28.0, 22.3};
```

Se você especificar um tamanho, mas fornecer menos inicializadores, os elementos restantes serão inicializados com zero (para tipos numéricos) ou caractere nulo ('\0' para `char`).

```c
int outros_numeros[5] = {10, 20}; // outros_numeros[0] = 10, outros_numeros[1] = 20, outros_numeros[2] = 0, outros_numeros[3] = 0, outros_numeros[4] = 0
```

### 2. Strings: Vetores de Caracteres Especiais

No contexto de vetores, é fundamental entender o que é uma **string** em C.

**Definição:** Em C, uma **string** é simplesmente um **vetor de caracteres** terminado por um caractere especial chamado **caractere nulo** (`\0`). Este caractere nulo sinaliza o final da string.

**Por que o caractere nulo?**

Como um vetor de caracteres tem um tamanho fixo definido na declaração, o caractere nulo é essencial para que as funções que manipulam strings (como `printf` para imprimir) saibam onde a string realmente termina, mesmo que o vetor tenha mais espaço alocado.

**Declaração e Inicialização de Strings:**

Existem algumas maneiras comuns de declarar e inicializar strings em C:

```c
char palavra1[10] = "Olá"; // Cria um vetor de 10 caracteres e inicializa com "Olá\0"
char palavra2[] = "Mundo"; // O tamanho é inferido como 6 (5 letras + '\0')
char palavra3[6];         // Declara um vetor de 6 caracteres (precisa ser preenchido depois)
char letras_array[] = {'C', 'a', 's', 'a', '\0'}; // Inicialização explícita com o caractere nulo
```

**Importante:** Ao declarar um vetor para armazenar uma string, lembre-se de reservar espaço para o caractere nulo no final. Se você quer armazenar uma string de 5 caracteres, precisa de um vetor de pelo menos 6 posições.

**Manipulando Strings:**

C possui uma biblioteca padrão (<string.h>) que oferece diversas funções para manipular strings, como:

* `strlen(string)`: Retorna o comprimento da string (o número de caracteres antes do '\0').
* `strcpy(destino, origem)`: Copia a string `origem` para a string `destino`.
* `strcat(destino, origem)`: Concatena (junta) a string `origem` ao final da string `destino`.
* `strcmp(string1, string2)`: Compara duas strings. Retorna 0 se forem iguais, um valor negativo se `string1` vier antes de `string2` na ordem alfabética, e um valor positivo caso contrário.

**Exemplo: Contando a Frequência de uma Letra em uma Frase:**

Vamos criar um programa que conta quantas vezes uma determinada letra aparece em uma frase inserida pelo usuário.

```c
#include <stdio.h>
#include <string.h>
#include <ctype.h> // Para usar a função tolower

int main() {
    char frase[100];
    char letra_procurada;
    int contador = 0;
    int i;

    printf("Digite uma frase: ");
    fgets(frase, sizeof(frase), stdin); // Lê a frase do usuário (incluindo espaços)

    // Remove a quebra de linha ('\n') que fgets pode adicionar
    frase[strcspn(frase, "\n")] = 0;

    printf("Digite a letra que deseja contar: ");
    scanf(" %c", &letra_procurada); // Note o espaço antes de %c para consumir espaços em branco

    // Converter a letra procurada para minúsculo para comparação case-insensitive
    char letra_minuscula = tolower(letra_procurada);

    // Percorrer cada caractere da frase
    for (i = 0; frase[i] != '\0'; i++) {
        // Converter o caractere da frase para minúsculo para comparação
        if (tolower(frase[i]) == letra_minuscula) {
            contador++;
        }
    }

    printf("A letra '%c' aparece %d vezes na frase.\n", letra_procurada, contador);

    return 0;
}
```

**Explicação do Código:**

1.  **Inclusão de Bibliotecas:**
    * `stdio.h`: Para funções de entrada e saída (como `printf` e `fgets`).
    * `string.h`: Para funções de manipulação de strings (como `strlen` e `strcspn`).
    * `ctype.h`: Para funções de manipulação de caracteres (como `tolower`).

2.  **Declaração de Variáveis:**
    * `frase[100]`: Um vetor de caracteres para armazenar a frase digitada pelo usuário (com capacidade para até 99 caracteres + o '\0').
    * `letra_procurada`: Uma variável do tipo `char` para armazenar a letra que o usuário quer contar.
    * `contador`: Uma variável inteira para armazenar a contagem da letra.
    * `i`: Uma variável inteira para usar como índice no loop.

3.  **Entrada da Frase:**
    * `printf("Digite uma frase: ");`: Exibe uma mensagem pedindo ao usuário para digitar uma frase.
    * `fgets(frase, sizeof(frase), stdin);`: Lê a frase digitada pelo usuário e armazena no vetor `frase`. `fgets` é mais seguro que `scanf` para ler strings, pois evita estouros de buffer.
    * `frase[strcspn(frase, "\n")] = 0;`: Remove a possível quebra de linha (`\n`) que o `fgets` pode adicionar ao final da string.

4.  **Entrada da Letra:**
    * `printf("Digite a letra que deseja contar: ");`: Exibe uma mensagem pedindo a letra a ser contada.
    * `scanf(" %c", &letra_procurada);`: Lê um único caractere digitado pelo usuário e armazena em `letra_procurada`. O espaço antes de `%c` ajuda a consumir quaisquer espaços em branco ou quebras de linha pendentes no buffer de entrada.

5.  **Conversão para Minúsculo:**
    * `char letra_minuscula = tolower(letra_procurada);`: Converte a letra procurada para minúsculo usando a função `tolower`. Isso torna a contagem *case-insensitive* (ou seja, 'a' e 'A' serão contados da mesma forma).

6.  **Loop para Contar a Letra:**
    * `for (i = 0; frase[i] != '\0'; i++) { ... }`: Este loop percorre cada caractere da string `frase` até encontrar o caractere nulo (`\0`), que marca o final da string.
    * `if (tolower(frase[i]) == letra_minuscula) { contador++; }`: Dentro do loop, cada caractere da frase é convertido para minúsculo e comparado com a `letra_minuscula`. Se forem iguais, o `contador` é incrementado.

7.  **Exibição do Resultado:**
    * `printf("A letra '%c' aparece %d vezes na frase.\n", letra_procurada, contador);`: Exibe o resultado da contagem para o usuário.

### 3. Matrizes (Arrays Bidimensionais): Tabelas de Dados

Agora, vamos imaginar que precisamos guardar as notas de vários alunos em várias disciplinas. Um vetor simples não seria suficiente para organizar esses dados de forma clara. É aí que entram as **matrizes**.

**Definição:** Uma matriz é uma estrutura de dados que armazena elementos do **mesmo tipo** em um formato de **tabela**, com linhas e colunas. Podemos pensar em uma matriz como um "vetor de vetores". Cada elemento na matriz é acessado por dois índices: um para a linha e outro para a coluna.

**Analogia:** Pense em uma planilha do Excel. Ela tem linhas e colunas, e cada célula na planilha armazena um valor. A matriz funciona de forma semelhante.

**Declaração de uma Matriz em C:**

A sintaxe geral para declarar uma matriz em C é:

```c
tipo nome_da_matriz[numero_de_linhas][numero_de_colunas];
```

**Exemplos:**

* Uma matriz para armazenar as notas de 3 alunos em 4 disciplinas (inteiros):
    ```c
    int notas_alunos[3][4]; // 3 linhas (alunos), 4 colunas (disciplinas)
    ```

* Uma matriz para representar um tabuleiro de xadrez (caracteres):
    ```c
    char tabuleiro[8][8]; // 8 linhas, 8 colunas
    ```

**Acessando Elementos da Matriz:**

Para acessar um elemento específico da matriz, usamos o nome da matriz seguido dos índices da linha e da coluna entre colchetes. Lembre-se que a indexação começa em 0 para ambas as dimensões.

```c
#include <stdio.h>

int main() {
    int matriz[2][3]; // Matriz com 2 linhas e 3 colunas

    matriz[0][0] = 1; // Elemento na primeira linha (índice 0), primeira coluna (índice 0)
    matriz[0][1] = 2; // Elemento na primeira linha (índice 0), segunda coluna (índice 1)
    matriz[0][2] = 3; // Elemento na primeira linha (índice 0), terceira coluna (índice 2)
    matriz[1][0] = 4; // Elemento na segunda linha (índice 1), primeira coluna (índice 0)
    matriz[1][1] = 5; // Elemento na segunda linha (índice 1), segunda coluna (índice 1)
    matriz[1][2] = 6; // Elemento na segunda linha (índice 1), terceira coluna (índice 2)

    printf("O elemento na linha 0, coluna 1 é: %d\n", matriz[0][1]); // Saída: O elemento na linha 0, coluna 1 é: 2
    printf("O elemento na linha 1, coluna 2 é: %d\n", matriz[1][2]); // Saída: O elemento na linha 1, coluna 2 é: 6

    return 0;
}
```

**Inicialização de Matrizes:**

Podemos inicializar os elementos de uma matriz no momento da declaração usando chaves aninhadas:

```c
int tabela[2][2] = {
    {10, 20}, // Inicializa a primeira linha
    {30, 40}  // Inicializa a segunda linha
};

char mapa[3][3] = {
    {'X', 'O', ' '},
    {' ', 'X', ' '},
    {'O', ' ', 'X'}
};
```

Também é possível inicializar todos os elementos em uma única lista, mas a forma aninhada geralmente melhora a legibilidade:

```c
int outra_tabela[2][2] = {10, 20, 30, 40}; // Equivalente ao exemplo anterior
```

**Iterando sobre Matrizes:**

Para processar todos os elementos de uma matriz, geralmente usamos loops aninhados: um loop para percorrer as linhas e outro loop para percorrer as colunas de cada linha.

```c
#include <stdio.h>

int main() {
    int matriz_exemplo[2][3] = {{1, 2, 3}, {4, 5, 6}};
    int i, j;

    printf("Elementos da matriz:\n");
    for (i = 0; i < 2; i++) {      // Loop para as linhas
        for (j = 0; j < 3; j++) {  // Loop para as colunas
            printf("%d ", matriz_exemplo[i][j]);
        }
        printf("\n"); // Mudar de linha após cada linha da matriz ser impressa
    }

    return 0;
}
```

**Saída:**

```
Elementos da matriz:
1 2 3
4 5 6
```
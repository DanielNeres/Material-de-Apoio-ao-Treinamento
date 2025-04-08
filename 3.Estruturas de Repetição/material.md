# Estruturas de Repetição em C

## Introdução
As estruturas de repetição são mecanismos que permitem executar um bloco de código múltiplas vezes, de forma controlada. Na programação, elas são essenciais para automatizar tarefas repetitivas, processar conjuntos de dados e criar comportamentos contínuos em sistemas.

Em nosso dia a dia, realizamos diversos loops naturais: ao escovar os dentes, repetimos os mesmos movimentos por um tempo determinado; quando esperamos um ônibus, ficamos em um "loop" de verificar o relógio e olhar para a rua até que ele chegue; ou mesmo ao ler um livro, viramos páginas até alcançar o final. Essas estruturas nos cercam - sempre que há repetição com um critério de parada, temos a essência de um loop de programação.

**Funcionamento:**
O `while` avalia uma condição antes de cada iteração. Se verdadeira, executa o bloco; se falsa, encerra o loop.

**Sintaxe Profunda:**
```c
while (expressão_booleana) {
    // Corpo do loop
    // Deve conter lógica que afete a condição
}
```

**Exemplo:**
```c
#include <stdio.h>
#include <time.h>

int main() {
    int segundos_restantes = 10;
    
    printf("Contagem regressiva iniciada:\n");
    while (segundos_restantes > 0) {
        printf("%d...\n", segundos_restantes);
        sleep(1); // Pausa de 1 segundo
        segundos_restantes--; // Alteração crucial da condição
    }
    
    printf("Foguete lançado!\n");
    return 0;
}
```

**Pontos Críticos:**
- **Condição de entrada**: Só entra no loop se a condição for verdadeira
- **Variável de controle**: Deve ser modificada dentro do loop
- **Loop infinito**: Ocorre se a condição nunca se tornar falsa

**Caso de Uso Ideal:**
Quando o número de iterações é desconhecido a priori, mas há uma condição clara de parada.

### Desafio 1.1
Implemente um sistema de login que dá 3 tentativas ao usuário. A cada tentativa falha, mostre quantas chances restam. Se acertar, conceda acesso imediato.

---

## 2. O Loop `do-while` - Execute Primeiro, Pergunte Depois

**Diferença Fundamental:**
Executa o bloco pelo menos uma vez antes de verificar a condição.

**Estrutura Detalhada:**
```c
do {
    // Corpo do loop
} while (condição);
```

**Exemplo Complexo:**
```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char continuar;
    float total = 0;
    
    do {
        float valor;
        printf("Digite o valor da transação: ");
        scanf("%f", &valor);
        
        total += valor;
        
        printf("Deseja registrar outra transação? (S/N): ");
        scanf(" %c", &continuar);
        continuar = toupper(continuar);
        
    } while (continuar == 'S');
    
    printf("Total acumulado: R$ %.2f\n", total);
    return 0;
}
```

**Análise Comportamental:**
1. Sempre executa o bloco pelo menos uma vez
2. A condição é avaliada após cada execução
3. Ideal para menus e interações que devem ocorrer ao menos uma vez

### Desafio 2.1
Implemente uma calculadora interativa que repete até o usuário sair, com histórico das últimas 5 operações.

### Desafio 2.2
Desenvolva um sistema de palpite numérico onde o programa diz se o chute foi alto ou baixo, repetindo até acertar.

---

## 3. O Loop `for` - Controle Preciso de Iterações

**Arquitetura Completa:**
```c
for (inicialização; condição; incremento) {
    // Corpo do loop
}
```

**Exemplo:**
```c
#include <stdio.h>

int main() {
    // contando ate cem
    for (int i = 1; i <= 100; ++i) {
        printf("%d\n", i);
    }
    
    return 0;
}
```

**Componentes Essenciais:**
1. **Inicialização**: Executada uma única vez no início
2. **Condição**: Avaliada antes de cada iteração
3. **Incremento**: Executado após cada iteração

### Desafio 3.1
Implemente a sequência de Fibonacci até um termo N usando um único loop for, sem arrays.

### Desafio 3.2
Crie um programa que decomponha um número em seus fatores primos.

---

## 4. Controle de Fluxo em Loops

**Comandos Especiais:**
1. `break`: Interrompe imediatamente a execução do loop
2. `continue`: Pula para a próxima iteração do loop
3. `goto` (uso cauteloso): Transfere controle para um rótulo

**Exemplo Prático:**
```c
#include <stdio.h>
#include <stdbool.h>

int main() {
    while (true) {
        int numero;
        printf("Digite um número entre 1-100 (0 para sair): ");
        scanf("%d", &numero);
        
        if (numero == 0) {
            printf("Encerrando...\n");
            break;
        }
        
        if (numero < 1 || numero > 100) {
            printf("Valor inválido!\n");
            continue;
        }
        
        printf("Quadrado: %d\n", numero * numero);
    }
    
    return 0;
}
```

**Padrões Comuns:**
- Loops infinitos com saída condicional (while(true))
- Validação de entrada com continue
- Saída antecipada com break

### Desafio 4.1
Implemente um jogo de adivinhação com dicas, limite de tentativas e opção de desistência.

### Desafio 4.2
Crie um menu de opções com validação de entrada e tratamento de erros robusto.

---

## 5. Loops Aninhados

**Estrutura Típica:**
```c
for (int i = 0; i < linhas; i++) {
    for (int j = 0; j < colunas; j++) {
        // Processamento bidimensional
    }
}
```

**Exemplo:**
```c
#include <stdio.h>

int main() {
    int tamanho;
    
    printf("Digite o tamanho do quadrado (1-20): ");
    scanf("%d", &tamanho);
    
    for (int linha = 0; linha < tamanho; linha++) {
        for (int coluna = 0; coluna < tamanho; coluna++) {
            printf("# ");
        }
        printf("\n");
    }
    
    return 0;
}
```


### Desafio 5.1
Implemente uma tabuada completa formatada como tabela, com alinhamento de colunas.

### Desafio 5.2
Desenvolva um algoritmo para encontrar todos os números primos até N.

---

## Solução do Torneio de Tênis com Loops

```c
#include <stdio.h>

int main() {
    int vitorias = 0;
    char resultado;
    
    printf("Digite os resultados dos 6 jogos (V para vitória, P para derrota):\n");
    
    for (int jogo = 1; jogo <= 6; jogo++) {
        printf("Jogo %d: ", jogo);
        scanf(" %c", &resultado);
        
        if (resultado == 'V') {
            vitorias++;
        } else if (resultado != 'P') {
            printf("Entrada inválida! Use apenas V ou P.\n");
            jogo--; // Repete a iteração
        }
    }
    
    if (vitorias >= 5) {
        printf("1\n");
    } else if (vitorias >= 3) {
        printf("2\n");
    } else if (vitorias >= 1) {
        printf("3\n");
    } else {
        printf("-1\n");
    }
    
    return 0;
}
```
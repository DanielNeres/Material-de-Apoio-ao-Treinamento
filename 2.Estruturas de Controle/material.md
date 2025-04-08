# Estruturas de Verificação

## 1. Introdução
Imagine um segurança de boate que decide quem pode entrar. Ele faz verificações:
- "Você tem mais de 18 anos?" (Uma pergunta: [if] Se? se sim entra, [else] se não barrado)

As estruturas de verificação são como esses portões lógicos que direcionam o fluxo do programa.

## 2. Operadores Relacionais
Usados para comparar valores:

| Operador | Descrição          | Exemplo | Resultado |
|----------|--------------------|---------|-----------|
| ==       | Igual a            | 5 == 5  | 1 (true)  |
| !=       | Diferente de       | 5 != 3  | 1         |
| >        | Maior que          | 5 > 3   | 1         |
| <        | Menor que          | 5 < 3   | 0 (false) |
| >=       | Maior ou igual a   | 5 >= 5  | 1         |
| <=       | Menor ou igual a   | 5 <= 3  | 0         |

**Exemplo:**
```c
int a = 5, b = 3;
printf("%d\n", a == b);  // Imprime 0 (false)
```

---

## 2. Estrutura `if` Simples
Um único portão lógico que só abre se a condição for verdadeira.

**Funcionamento:**
```c
if (condição) {
    // Bloco de código executado
    // APENAS quando a condição for verdadeira
}
```

**Exemplo:**
```c
#include <stdio.h>

int main() {
    int temperatura;
    printf("Digite a temperatura atual: ");
    scanf("%d", &temperatura);
    
    // Verificação única
    if (temperatura > 30) {
        printf("Alerta! Temperatura acima do normal.\n");
        printf("Ativar sistema de resfriamento.\n");
    }
    
    printf("Continuação do programa...\n");
    return 0;
}
```

**Mecanismo de Funcionamento:**
1. A condição é avaliada (convertida para 0 ou 1)
2. Se diferente de 0 (true), executa o bloco
3. Independente do resultado, continua após o bloco

### Desafio 2.1
Implemente um sistema de autenticação ultra-restritivo que só permita acesso se:
- O código digitado for exatamente 3223
- E o segundo código for múltiplo de 17
Mostre mensagens específicas para cada erro de verificação.

---

## 3. Estrutura `if-else`
Portão com duas saídas obrigatórias - uma para true, outra para false.

**Funcionamentoa:**
```c
if (condição) {
    // Bloco TRUE
    // Executado quando a condição é verdadeira
} else {
    // Bloco FALSE
    // Executado quando a condição é falsa
    // O else "captura" todos os casos não atendidos pelo if
}
```

**Exemplo:**
```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char classificacao;
    printf("Digite a classificação do produto (A-E): ");
    scanf(" %c", &classificacao);
    
    if (toupper(classificacao) == 'A') {
        printf("Produto Premium - Garantia 5 anos\n");
        printf("Acesso à assistência 24h\n");
    } else {
        printf("Produto Standard - Garantia 1 ano\n");
        printf("Atendimento das 8h às 18h\n");
    }
    
    return 0;
}
```

**Fluxo de Execução:**
1. Avalia a condição exatamente como no if simples
2. Executa APENAS UM dos blocos (nunca ambos)
3. O bloco else é opcional, mas quando presente, é executado para qualquer condição não verdadeira

### Desafio 3.1
Crie um sistema de diagnóstico médico que:
- Receba 5 sintomas (febre, tosse, etc.) como variáveis booleanas (0/1)
- Se pelo menos 3 sintomas estiverem presentes, classifique como "Grupo de Risco"
- Caso contrário, mas com febre, classifique como "Observação"
- Nos outros casos, "Liberado"

---

## 4. Estrutura `if-else if-else`
Série de portões encadeados com múltiplas condições exclusivas.

**Funcionamento:**
```c
if (condição1) {
    // Bloco 1
} else if (condição2) {
    // Bloco 2
} else if (condição3) {
    // Bloco 3
} else {
    // Bloco else final (opcional)
}
```

**Exemplo:**
```c
#include <stdio.h>
#include <math.h>

int main() {
    double imc;
    printf("Calculadora de IMC\n");
    printf("Digite seu IMC: ");
    scanf("%lf", &imc);
    
    if (isnan(imc) {
        printf("Valor inválido!\n");
    } else if (imc < 18.5) {
        printf("Abaixo do peso\n");
        printf("Recomendação: Aumentar ingestão calórica\n");
    } else if (imc < 25) {
        printf("Peso normal\n");
        printf("Manter hábitos saudáveis\n");
    } else if (imc < 30) {
        printf("Sobrepeso\n");
        printf("Recomendação: Aumentar atividade física\n");
    } else if (imc < 35) {
        printf("Obesidade Grau I\n");
        printf("Procure orientação médica\n");
    } else {
        printf("Obesidade Grau II ou superior\n");
        printf("Acompanhamento médico urgente\n");
    }
    
    return 0;
}
```

**Ordem de Avaliação Crítica:**
1. As condições são verificadas em sequência
2. Quando uma é verdadeira, seu bloco é executado e as demais são ignoradas
3. O bloco else final captura todos os casos não cobertos

### Desafio 4.1
Implemente um sistema de tarifação de energia com as seguintes regras:
- Consumo até 30KWh: R$ 0.50/KWh
- Acima de 30 até 100KWh: R$ 0.75/KWh para o excedente
- Acima de 100KWh: R$ 1.20/KWh para o excedente
- Taxa extra de 10% se consumo > 200KWh
Mostre a conta detalhada com valores parciais.

---


## 4. Operadores Lógicos
Combinam condições:

| Operador | Descrição        | Exemplo            |
|----------|------------------|--------------------|
| &&       | AND lógico       | (a > 0) && (a < 10)|
| \|\|     | OR lógico        | (a == 0) \|\| (b == 0)|
| !        | NOT lógico       | !(a == b)          |

**Exemplo:**
```c
int num = 15;
if (num > 0 && num % 2 == 0) {
    printf("Número positivo e par\n");
}
```

### Desafio 4.1
Verifique se um número está entre 10 e 100 (inclusive).

### Desafio 4.2
Peça três números e verifique se pelo menos dois são iguais.

---

## 5. Estrutura switch-case
Alternativa para múltiplos if-else quando se testa uma única variável.

**Exemplo:**
```c
#include <stdio.h>

int main() {
    char op;
    printf("Digite uma opção (A, B ou C): ");
    scanf(" %c", &op);
    
    switch(op) {
        case 'A':
            printf("Opção A selecionada\n");
            break;
        case 'B':
            printf("Opção B selecionada\n");
            break;
        case 'C':
            printf("Opção C selecionada\n");
            break;
        default:
            printf("Opção inválida\n");
    }
    
    return 0;
}
```

**Importante:**
- Sempre usar `break` para evitar fallthrough
- `default` cobre casos não especificados

### Desafio 5.1
Crie um menu de calculadora com switch-case para as 4 operações básicas.

### Desafio 5.2
Faça um programa que converta números de 1 a 5 em seus equivalentes por extenso ("um", "dois", etc).

---

## 6. Operador Ternário
Forma compacta de if-else.

**Sintaxe:**
```c
condição ? expressão_se_verdadeiro : expressão_se_falso;
```

**Exemplo:**
```c
int a = 5, b = 3;
int maior = (a > b) ? a : b;
```

### Desafio 6.1
Reescreva o Desafio 2.1 usando operador ternário.

### Desafio 6.2
Use o operador ternário para determinar se um número é par ou ímpar.

---

## 7. Aninhamento de Estruturas
É possível colocar estruturas de verificação dentro de outras.

**Exemplo:**
```c
if (conta_ativa) {
    if (saldo >= valor) {
        printf("Saque autorizado\n");
    } else {
        printf("Saldo insuficiente\n");
    }
} else {
    printf("Conta inativa\n");
}
```

### Desafio 7.1
Crie um sistema de login que verifique usuário E senha.

### Desafio 7.2
Classifique um triângulo (equilátero, isósceles ou escaleno) com base nos lados fornecidos.

---

## Boas Práticas
1. Sempre usar chaves `{}` mesmo para blocos de uma linha
2. Manter condições simples e legíveis
3. Evitar aninhamento muito profundo (mais de 3 níveis)
4. Usar switch-case para múltiplas condições sobre uma mesma variável
5. Comentar condições complexas

### Desafio Final
Crie um programa completo que:
1. Peça três notas de um aluno
2. Calcule a média
3. Classifique conforme:
   - Aprovado (média ≥ 7)
   - Recuperação (5 ≤ média < 7)
   - Reprovado (média < 5)
4. Para aprovados, verifique se foi com louvor (média ≥ 9)


### Questão OBI

##Torneio de tênis
A prefeitura contratou um novo professor para ensinar as crianças do bairro a jogar tênis na quadra de tênis do parque municipal. O professor convidou todas as crianças do bairro interessadas em aprender a jogar tênis. Ao final do primeiro mês de aulas e treinamentos foi organizado um torneio em que cada participante disputou exatamente seis jogos. O professor vai usar o desempenho no torneio para separar as crianças em três grupos, de forma a ter grupos de treino em que os participantes tenham habilidades mais ou menos iguais, usando o seguinte critério:

-participantes que venceram 5 ou 6 jogos serão colocados no Grupo 1;
-participantes que venceram 3 ou 4 jogos serão colocados no Grupo 2;
-participantes que venceram 1 ou 2 jogos serão colocados no Grupo 3;
-participantes que não venceram nenhum jogo não serão convidados a continuar com os treinamentos.
Dada uma lista com o resultado dos jogos de um participante, escreva um programa para determinar em qual grupo ele será colocado.
Entrada
A entrada consiste de seis linhas, cada linha indicando o resultado de um jogo do participante. Cada linha contém um único caractere: V se o participante venceu o jogo, ou P se o jogador perdeu o jogo. Não há empates nos jogos.
Saída
Seu programa deve produzir uma única linha na saída, contendo um único inteiro, identificando o grupo em que o participante será colocado. Se o participante não for colocado em nenhum dos três grupos seu programa deve imprimir o valor -1.


## 5. Torneio de Tênis (Solução Comentada)

```c
#include <stdio.h>

int main() {
    char resultado;
    int vitorias = 0;
    
    // Lendo os 6 jogos
    printf("Digite os resultados dos 6 jogos (V/P):\n");
    
    // Jogo 1
    printf("Jogo 1: ");
    scanf(" %c", &resultado);
    if (resultado == 'V') vitorias++;
    
    // Jogo 2
    printf("Jogo 2: ");
    scanf(" %c", &resultado);
    if (resultado == 'V') vitorias++;
    
    // Jogo 3
    printf("Jogo 3: ");
    scanf(" %c", &resultado);
    if (resultado == 'V') vitorias++;
    
    // Jogo 4
    printf("Jogo 4: ");
    scanf(" %c", &resultado);
    if (resultado == 'V') vitorias++;
    
    // Jogo 5
    printf("Jogo 5: ");
    scanf(" %c", &resultado);
    if (resultado == 'V') vitorias++;
    
    // Jogo 6
    printf("Jogo 6: ");
    scanf(" %c", &resultado);
    if (resultado == 'V') vitorias++;
    
    // Determinando o grupo
    if (vitorias >= 5) {
        printf("1\n");  // Grupo 1
    } 
    else if (vitorias >= 3) {
        printf("2\n");  // Grupo 2
    }
    else if (vitorias >= 1) {
        printf("3\n");  // Grupo 3
    }
    else {
        printf("-1\n"); // Não convidado
    }
    
    return 0;
}
```

**Análise da Solução:**
1. **Contagem de vitórias**: Usamos uma variável acumuladora (`vitorias`) para contar quantos 'V's foram digitados
2. **Leitura segura**: O espaço antes do `%c` evita problemas com caracteres de nova linha
3. **Estrutura de decisão**:
   - Começamos pela condição mais restritiva (5-6 vitórias)
   - Depois verificamos as faixas decrescentes
   - O `else` final captura o caso de nenhuma vitória
4. **Saída**: Imprime apenas o número do grupo ou -1 conforme especificado

**Teste de Casos:**
- Entrada: V V V V V V → Saída: 1
- Entrada: V P V P V P → Saída: 2
- Entrada: P P V P P P → Saída: 3
- Entrada: P P P P P P → Saída: -1

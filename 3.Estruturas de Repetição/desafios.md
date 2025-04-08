
### **1. Sistema de Segurança de Banco**  
**Contexto**:  
Um cofre eletrônico só se desbloqueia após **três tentativas consecutivas com senhas válidas**. Cada senha válida deve:  
- Ter exatamente 6 dígitos  
- Conter pelo menos um número primo (2, 3, 5, 7)  
- A soma dos dígitos ser par  

Se uma senha inválida for inserida, o sistema reinicia a contagem.  

**Entrada**:  
Sequência de senhas (uma por linha) até o cofre ser desbloqueado.  

**Saída**:  
1. `SUCESSO` + número total de tentativas  
2. Se o cofre não desbloqueou após 20 tentativas: `BLOQUEADO`  

**Exemplo 1**:  
Entrada:  
```
123456  
234567  
345678  
```  
Saída: `BLOQUEADO (3 tentativas)`  
*Explicação*:  
- 123456: Primo (2,3,5), soma=21 (ímpar) → inválida  
- 234567: Primo (2,3,5,7), soma=27 (ímpar) → inválida  
- 345678: Primo (3,5,7), soma=33 (ímpar) → inválida  


---

### **2. Controle de Qualidade em Fábrica**  
**Contexto**:  
Uma esteira industrial produz peças com IDs únicos. O sistema deve:  
Ler IDs e encontrar **IDs com dígitos repetidos** (ex: 1212, 3333)  

**Entrada**:  
IDs de 4 dígitos (um por linha).  

**Saída**:  
IDs problemáticos  

**Exemplo**:  
Entrada:  
```
1234  
5678  
1122  
3344  
```  
Saída:  
```
IDs inválidos: 1122 e 3344  
```  

---

### **3. Torneio de Xadrez por Resistência**  
**Contexto**:  
Dois jogadores disputam partidas até que um tenha **três vitórias consecutivas** ou **cinco vitórias no total**. Cada resultado é:  
- `V` para vitória do jogador 1  
- `D` para vitória do jogador 2  

**Entrada**:  
Sequência de resultados (ex: `VVDVDDD`).  

**Saída**:  
1. Vencedor (`Jogador 1` ou `Jogador 2`)  
2. Motivo (`sequência` ou `total`)  
3. Número de partidas  

**Exemplo 1**:  
Entrada: `V V D V V V`  
Saída:  
```
Jogador 1 venceu por sequência (6 partidas)  
```  

**Exemplo 2**:  
Entrada: `D D V D D V D `  
Saída:  
```
Jogador 2 venceu por total (5 vitórias em 7 partidas)  
```  

---

### **4. Monitoramento de Tráfego em Metrô**  
**Contexto**:  
Um sistema registra o número de passageiros que entram/saem em estações até detectar **superlotação crítica**:  
- Passageiros > 200 em uma estação  
- **E** aumento de 50% em relação à média das últimas 5 estações  

**Entrada**:  
Números inteiros (passageiros por estação), um por linha.  

**Saída**:  
1. Estação crítica  
2. Média das 5 estações anteriores  

**Exemplo**:  
Entrada:  
```
100  
120  
90  
150  
180  
300  
```  
Saída:  
```
Estação 6 crítica (300 passageiros)  
Média anterior: 128.00  
```  


---

### **5. Controle de Epidemias em Hospital**  
**Contexto**:  
Um hospital monitora casos de uma doença até haver **Um aumento de casos ≥ 20%**.


**Entrada**
Novos casos  

**Saída**:  
Taxa de crescimento do ultimo registro

**Exemplo**:  
Entrada:  
```
55  
60  
72  
70  
100  
```  
Saída:  
```
42%
```
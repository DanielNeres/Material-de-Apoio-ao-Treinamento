
### **1. Validação de Senha com Vetores**  
**Contexto**:  
Um sistema exige senhas que contenham pelo menos:  
- 1 letra maiúscula  
- 1 número  
- 1 caractere especial (`!`, `@`, `#`, `$`)  

**Entrada**:  
Uma string (ex: `"Senha#123"`).  

**Saída**:  
`VÁLIDA` ou `INVÁLIDA`.  

**Exemplo**:  
Entrada: `"Abc!2024"`  
Saída: `VÁLIDA`  

---

### **2. Contagem de Elementos Únicos**  
**Contexto**:  
Dado um vetor de números, conte quantos elementos aparecem **exatamente uma vez**.  

**Entrada**:  
- Primeira linha: `N` (tamanho do vetor)  
- Segunda linha: `N` números inteiros  

**Saída**:  
Número de elementos únicos.  

**Exemplo**:  
Entrada:  
```  
5  
2 4 2 7 4  
```  
Saída: `1` (apenas o 7 é único)  

---

### **3. Inversão de String com Restrição**  
**Contexto**:  
Inverta uma string, mas mantenha a ordem dos números (dígitos 0-9) inalterada.  

**Entrada**:  
Uma string (ex: `"a1b2c"`).  

**Saída**:  
String invertida com números na posição original.  

**Exemplo**:  
Entrada: `"x3y#z"`  
Saída: `"z3y#x"`  

---

### **4. Verificação de Matriz Identidade**  
**Contexto**:  
Verifique se uma matriz quadrada é uma **matriz identidade** (1s na diagonal principal, 0s nos demais).  

**Entrada**:  
- Primeira linha: `N` (tamanho da matriz)  
- `N` linhas seguintes: elementos da matriz  

**Saída**:  
`SIM` ou `NÃO`.  

**Exemplo**:  
Entrada:  
```  
3  
1 0 0  
0 1 0  
0 0 1  
```  
Saída: `SIM`  

---

### **5. Busca de OBI na Matriz**  
**Contexto**:  
Verifique se a palavra `"OBI"` aparece na horizontal ou vertical em uma matriz de caracteres.  

**Entrada**:  
- Primeira linha: `N` (tamanho da matriz N x N)  
- `N` linhas seguintes: caracteres (cada linha contém `N` letras maiúsculas)  

**Saída**:  
`SIM` se encontrar a palavra, `NÃO` caso contrário.  

**Exemplo**:  
Entrada:  
```  
3  
O B I  
B I K  
C C O  
```  
Saída: `SIM` 

---

### **6. Frequência de Caracteres**  
**Contexto**:  
Conte quantas vezes cada vogal (`A`, `E`, `I`, `O`, `U`) aparece em um texto.  

**Entrada**:  
Uma string (até 100 caracteres).  

**Saída**:  
5 números separados por espaço (ordem A, E, I, O, U).  

**Exemplo**:  
Entrada: `"OLIMPÍADA BRASILEIRA DE INFORMÁTICA"`  
Saída: `6 3 3 2 0`  

---

### **7. Soma de Colunas em Matriz**  
**Contexto**:  
Calcule a soma de cada coluna em uma matriz numérica.  

**Entrada**:  
- Primeira linha: `N` (tamanho N x N)  
- `N` linhas seguintes: elementos da matriz  

**Saída**:  
`N` números (somas das colunas).  

**Exemplo**:  
Entrada:  
```  
3  
1 2 3  
4 5 6  
7 8 9  
```  
Saída: `12 15 18`  

---

### **8. Ordenação de Vetor de Strings**  
**Contexto**:  
Ordene um vetor de strings em ordem alfabética.  

**Entrada**:  
- Primeira linha: `N` (número de strings)  
- `N` linhas seguintes: strings (sem espaços)  

**Saída**:  
Strings ordenadas, uma por linha.  

**Exemplo**:  
Entrada:  
```  
3  
banana  
abacaxi  
cereja  
```  
Saída:  
```  
abacaxi  
banana  
cereja  
```  

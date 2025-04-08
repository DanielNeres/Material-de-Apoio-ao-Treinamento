
### **1. Sistema de Emergência de Usina Nuclear**  
**Contexto**:  
Um sistema de segurança monitora 3 parâmetros críticos:  
- `Temperatura` (em °C)  
- `Pressão` (em kPa)  
- `Nível de Radiação` (em Sv/h)  

O protocolo de emergência é ativado se:  
1. Temperatura > 800 **E** Pressão > 10.000  
2. Radiação ≥ 50 **E** (Temperatura > 700 **OU** Pressão > 9.000)  
3. Todos os 3 parâmetros estiverem acima de 90% do limite máximo  

**Entrada**:  
Três números reais na ordem: `Temperatura Pressão Radiação`.  

**Saída**:  
"ATIVAR" ou "NORMAL".  

**Exemplo**:  
Entrada: `780 9500 49.9`  
Saída: `NORMAL`  

**Caso Complexo**:  
Entrada: `810 10001 40` → Saída: `ATIVAR` (Regra 1)  

---

### **2. Código Secreto da Resistência**  
**Contexto**:  
Para acessar o esconderijo da resistência, você deve decifrar um código com 4 dígitos (`ABCD`), onde:  
- `A + D = 15`  
- `B` é primo  
- `C` é múltiplo de 3  
- `A > D`  
- `B ≠ C`  

**Entrada**:  
Um número de 4 dígitos.  

**Saída**:  
"LIBERADO" se atender a **todas** as condições, "INVASOR" caso contrário.  

**Exemplo**:  
Entrada: `8537` → Saída: `LIBERADO` (A=8, B=5(primo), C=3(múltiplo de 3), D=7 → 8+7=15)  

**Desafio**:  
Entrada: `9436` → Saída: `INVASOR` (B=4 não é primo)  

---

### **3. Autenticação Biométrica de Alto Segurança**  
**Contexto**:  
Um sistema verifica 5 fatores biométricos:  
1. Digital (`D`: 0 ou 1)  
2. Íris (`I`: 0 ou 1)  
3. Frequência cardíaca (`H`: bpm)  
4. Assinatura térmica (`T`: °C)  
5. Resposta cerebral (`R`: mV)  

Acesso é concedido se:  
- (Digital **E** Íris) **OU**  
- (Frequência cardíaca entre 60-100 **E** Assinatura térmica entre 36.0-37.5) **OU**  
- (Resposta cerebral > 50 **E** Assinatura térmica < 35.0)  

**Entrada**:  
Cinco valores na ordem: `D I H T R`.  

**Saída**:  
"ACESSO PERMITIDO" ou "NEGADO".  

**Exemplo**:  
Entrada: `1 0 75 36.5 30` → Saída: `NEGADO`  
Entrada: `0 0 80 35.9 60` → Saída: `PERMITIDO` (Regra 3)  

---

### **4. Classificação de Emergência Médica**  
**Contexto**:  
Um sistema de triagem usa 3 indicadores:  
- `D`: Dor (1-10)  
- `S`: Sangramento (0=Nenhum, 1=Leve, 2=Grave)  
- `C`: Consciência (0=Inconsciente, 1=Alterada, 2=Normal)  

Prioridade é determinada por:  
- **P1 (Máxima)**: D ≥ 8 **E** (S=2 **OU** C=0)  
- **P2**: (D ≥ 5 **E** S=1) **OU** C=1  
- **P3**: Demais casos  

**Entrada**:  
Três inteiros: `D S C`.  

**Saída**:  
"P1", "P2", "P3" ou "INVALIDO" se dados inconsistentes.  

**Exemplo**:  
Entrada: `8 2 1` → Saída: `P1`  
Entrada: `7 1 1` → Saída: `P2`  

---

### **5. Decodificação de Mensagem Alienígena**  
**Contexto**:  
Uma mensagem recebida tem 3 símbolos (`X`, `Y`, `Z`) com as regras:  
- Valores válidos: 1 ≤ X,Y,Z ≤ 100  
- É uma mensagem de paz se:  
  `X` é par **E** `Y + Z` é múltiplo de 5  
- É uma mensagem de perigo se:  
  `X` é primo **OU** `Y * Z` > 1000  
- Caso contrário: mensagem desconhecida  

**Entrada**:  
Três inteiros: `X Y Z`.  

**Saída**:  
"PAZ", "PERIGO", "DESCONHECIDA" ou "INVALIDA".  

**Exemplo**:  
Entrada: `4 15 5` → Saída: `PAZ` (4 é par, 15+5=20)  
Entrada: `7 20 60` → Saída: `PERIGO` (7 é primo **E** 20*60=1200)  
lezione di [[Probabilità e Statistica]]
# **Set Operations in Probability**

#### Definizione

Le **Set Operations** in probabilità sono operazioni sugli eventi basate sulla **teoria degli insiemi**. Permettono di combinare eventi e calcolare probabilità di eventi composti.
### Operazioni Fondamentali

1.  **Unione ($A \cup B$) → "OR"**  
	Rappresenta **almeno uno** tra $A$ e $B$ che si verifica.
	$P(A∪B)=P(A)+P(B)−P(A∩B)P(A \cup B) = P(A) + P(B) - P(A \cap B)$
	Se $A$ e $B$ sono **mutuamente esclusivi**:
	$P(A∪B)=P(A)+P(B)P(A \cup B) = P(A) + P(B)$
2. **Intersezione ($A \cap B$) → "AND"**  
	Rappresenta **entrambi** gli eventi che si verificano.
	$P(A∩B)=P(A)P(B∣A)P(A \cap B) = P(A) P(B | A)$
	Se $A$ e $B$ sono **indipendenti**:
	$P(A∩B)=P(A)P(B)P(A \cap B) = P(A) P(B)$
3. **Complemento ($A^c$) → "NOT"**  
	Tutti gli esiti **non appartenenti** ad $A$.
	$P(Ac)=1−P(A)P(A^c) = 1 - P(A)$
4.  **Differenza ($A - B$) → "A ma non B"**  
	Tutti gli esiti che sono in $A$ **ma non** in $B$.
	$P(A−B)=P(A)−P(A∩B)P(A - B) = P(A) - P(A \cap B)$
### Proprietà Importanti

Legge della somma
- $P(A∪B)=P(A)+P(B)−P(A∩B)P(A \cup B) = P(A) + P(B) - P(A \cap B)$

Legge della probabilità totale
- Se ${A_1, A_2, ..., A_n}$ è una partizione di $\Omega$:

- $P(B)=∑iP(B∣Ai)P(Ai)P(B) = \sum_{i} P(B | A_i) P(A_i)$

Formula di Bayes

- $P(A∣B)=P(B∣A)P(A)P(B)P(A | B) = \frac{P(B | A) P(A)}{P(B)}$

Relazione con: [[Spazio di probabilità]], [[teorema di Bayes]]
[[Programmazione in C]]
## Definizione 
la aritmetica dei [[Puntatori]] è fondamentale per capire i puntatori. 
Dato un puntatore di un determinato tipo, aggiungere o sottrarre numeri ad esso andrà a far si che il nostro puntatore avanzi il numero di bit sufficienti per andare nel prossimo spazio in memoria dipendente dal numero che aggiungiamo. 

Dato quindi un int ` p++` andrà semplicemente a spostare il puntatore p di 4 byte (la dimensione di un int) e dopo possiamo scrivere nella nuova parte della memoria. 

Questo è importante per capire anche la [[Relazione tra stringhe e puntatori]]
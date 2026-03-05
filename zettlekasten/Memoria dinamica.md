[[Memoria nei sistemi operativi]]
## Definizione 
tutto ciò che ci permette di creare variabili (spesso in vettori ) senza sapere esattamente la dimensione di queste prima di inizializzare.

come abbiamo visto nel [[Layout della memoria]] questo è nel heap e cresce verso alto e tieni conto che ci sta anche il break.

per utilizzare tutto questo in Linux noi abbiamo delle funzioni di lib e tutte sono thread safe ma non sono ok nel signal handler 

questo in [[Programmazione in C]] abbiamo 
``` c
#include <stdlib.h>
void *malloc(size_t size); 
```
alloca size byte di memoria e ritorna il puntatore della memoria e non vengono inizializzare, se si vuole inizializzare a 0 usa calloc. altre:
- realloc: estende o riduce dimensione della allocazione di memoria 
- free: per liberare la memoria... se non lo fai hai il tuo memory leak 

Malloc non necessario per usare la memoria dinamica ma rende facile.

all'interno della malloc abbiamo una double linked list, lista linkata a elementi seguenti e precedenti che noi andiamo a liberare con la free.
La free riceve un puntatore alla memoria, ottiene la lunghezza, e va a cucire la lista ma non ci sono controlli quindi se sbagli ciao.
Ricordiamo inoltre che tutto questo è comandato da noi e attraverso funzioni di libreria mentre la nmap è in carica al kernel. 

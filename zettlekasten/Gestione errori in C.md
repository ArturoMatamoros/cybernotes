[[Programmazione in C]]
## Definizione 
La [[Gestione errori]] è fondamentale per capire se le operazioni sono andate con successo oppure no. 

la libreria standard `#include<errno.h>`di permette di utilizzare la variabile `int errno` che se fallisce da un codice di errore 

l'utilizzo è quello di confrontare gli errori con quello di cui ho bisogno.

è utile avere `void perror(const char *s);` è una funzione che stampa il tipo di errore. `char *strerror(int errnum);` anche.

attenzione, questo è un sistema obsoleto. 
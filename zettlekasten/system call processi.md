[[Processi e thread]]
## Funzione `wait` 
abbiamo visto la [[Creazione processi]] con fork, la wait è una funzione che va a bloccare il padre fino a quando il figlio è morto. 
Ritorna il PID del figlio terminato con 0 in caso di errore . 
- se il processo non ha figli : errore 
- se i figli sono terminati : ritorna istantaneamente 
- se ha figli che stanno ancora in piedi allora blocca il padre 

Il padre deve sempre invocare la wait altrimenti il processo figlio morto ma non sepolto è un processi zombie. Questo è diverso da orfano. 

La `pid_t waitpid(pid_t pid, int *status, int options);` è una funzione uguale ma qua ho anche options,`WNOHANG`

questa e la fork ci permettono di andare ad avere [[Grafi di precedenza]] ma non tutti dato che questi strumenti sono troppo semplici. 

## Funzione `exec`
exec sostituisce il programma di un processo. Questo è l'unico modo di eseguire un programma diverso. Qua vado a cambiare tutto in modo tale da avere un programma completamente diverso ma manteniamo: 
- variabili d'ambiente 
- PID e PPID 
- privilegi, current working directory, root e home directory 
cosa non viene ereditato: 
- file aperti se hanno il flag `close-on-exec`
- altrimenti vengono lasciati aperti 

abbiamo 7 versioni della exec, abbiamo bisogno di path e argomenti.
le variabili della exec con p alla fine vanno a cercare il programma invece di inserire il path

quelle con la l e v servono per passare argomenti. quando abbiamo la l dobbiamo listare gli argomenti uno alla volta ma con v abbiamo un vettore. Mentre se abbiamo quelle con la e possiamo avere un vettore di variabili d'ambiente. 

## funzione `system`
evoca un comando bash e ne attende la conclusione. Questa  va ad utilizzare fork, exec and wait per me e va ad usare programmi esterni in un programma 

## funzione di `exit`
in[[Programmazione in C]] questo succede quando si fa il return ma possiamo anche invocare la funzione `void exit(int status);` ma questa attenzione! NON E' UNA FUNZIONE [[System call]]!!! è una funzione di libreria. 

Quando andiamo ad invocare la exit noi andiamo a pulire tutto quello che riguarda il programma. Possiamo andare anche ad `atexit`che va a invocare una funzione prima di uscire con la exit.

Una volta pulito tutto noi andiamo ad uscire con la system call `_exit`ma noi non andiamo ad utilizzare questa se non una volta finita la exec
### Correlati 
[[Sistemi operativi]]
## Definizione
I thread in linux sono i flussi di esecuzione di un processo. Ogni uno ha un main thread ma alcuni processi hanno fratelli con altri flussi. 
- Questi condividono [[Memoria nei sistemi operativi]]
- eseguono lo stesso programma 

un processo con tanti thread significa che questi vanno a condividere ogni cosa, memoria e tutto, tranne lo stack. Lo stack ha infatti uno stack che viene creato automaticamente. 

Nella programmazione moderna noi abbiamo vari tread dato che la memoria è condivisa e possiamo farli comunicare con facilità e sfruttare la architettura multi-process e multi-thread. 

abbiamo: 
- kernel thread: messi a disposizione dal kernel con system call
	- questo è il più comune 
- user thread: creati dal programmatore o dalla libreria.
	- usato quando il kernel non supporta 
	- non sono banali, non li useremo quasi mai
### Correlato
- [[Pthread]] 
- [[Sincronizzazione]] 
- 

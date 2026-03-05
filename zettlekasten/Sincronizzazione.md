[[Thread]]
## Definizioni
un programma è **concorrente** : più flussi di esecuzione 
**parallelo**: più calcoli contemporaneamente 
un programma può essere concorrente senza essere parallelo e viceversa. 

L'obiettivo è qualcosa di sfruttare al massimo i core. Vale anche la legge di Amdahl: Tutto quello che non è in parallelo è un problema.

I mutex cercano di risolvere il problema della sezione critica. Ricordiamo che i thread hanno memoria condivisa e questo può essere un problema dato che può essere inefficiente. 

La soluzione è la sezione critica. Questa è una sezione di codice che deve essere atomica. Questa non possiamo interromperlo e solo una "persona" alla volta. Parliamo quindi di **Mutua esclusione** e si fa in: 
- un thread si prenota per l'accesso 
	- vi si accede 
	- si attende 
- al termine della sezione critica il thread rilascia la sezione 

Il mutex serve per andare a risolvere il problema in C implementando questo concetto e ha:
- locked 
- free
un thread ha due azioni:
- lock 
- release/unlock 

In C noi abbiamo nei [[Pthread]] variabili pthread_mutex_t e sono quelle che abbiamo visto in precedenza. Presta attenzione alla grammatica. 

Bisogna prestare attenzione al Deadlock, ovvero uno stallo in cui ogni thread attendono per entrare in una sezione critica che non si verificherà mai. Per evitare ciò allora usiamo pochi mutex utilizzando fifo e pipe, oppure usare tecniche matematiche complesse. 

## Correlati 
- [[Thread]]
	- [[Pthread]]
- [[Sezione critica]]
- [[Semafori]] 
- [[Problemi di sincronizazzione]] 
- [[Grafi di precedenza]] 

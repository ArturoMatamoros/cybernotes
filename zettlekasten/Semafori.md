[[Sincronizzazione]]
## Definizione 
I semafori sono numeri interi positivi condivisi. I thread possono:
- incrementare di 1 
- sottrarre 1 
siccome il semaforo è solo positivo questo è bloccato se qualche thread ha intenzione di sottrarre a 0 fino a quando qualcuno non lo sblocca andando ad incrementare. 

Questo ci permette di risolvere quasi tutti i problemi di sincronizzazione. In linux abbiamo 2 tipi di semafori: 
- system V che sono vecchi e complessi 
- posix semaphores che è la nostra version 

I posix possono essere: 
- named: usato da processi indipendenti 
- unnamed: possono essere usati solo da parenti
per il loro uso:
1. creazione 
2. processi effettuano:
	- post -> incremento 
	- wait -> decremento 
3. distruggere semaforo 

I Named si usano includendo semaphore.h e guarda i dettagli nelle slide. Il valore di ritorno è il semaforo se non è questo SEM_FAILED

per gli Unnamed fai lo stesso ma è anche più semplice degli altri. Guarda dettagli nella slide. Il punto è che è meglio usare un named quando si parla di applicazione multi processo 

Ma quando parliamo di un suo funzionamento chiaro bisogna di parlare del fatto che abbiamo bisogno di 2 semafori e non solo di 1.
## Correlati

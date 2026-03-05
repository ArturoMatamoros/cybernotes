[[Sincronizzazione]]
## [[Mutex]] e [[Semafori]]
costruire un mutex con un semaforo. Teniamo che il mutex è un semaforo inizializzato con un gettone. Tutto questo funziona ma bisogna prima di tutto fare attenzione a non avere più di 1 gettone. 
- questo lo puoi fare scrivendo sul unlock sempre un error handling

Costruire un semaforo con mutex ma non è il massimo. Il problema è creare una attesa quando il semaforo ha valore 0. Questo può essere facile da risolvere quando abbiamo compreso pienamente i semafori e la mutex. Il problema più grave è il fatto che la cpu è occupata in un loop dove si controlla quando andiamo a ottenere il gettone.

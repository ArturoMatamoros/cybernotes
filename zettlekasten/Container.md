[[Sistemi operativi]]
## Definizione 
Ci sono alcune limitazioni per nella [[Macchina virtuale]] e per andare a risolvere i problemi possiamo usare i container. La cosa più fondamentale che cerchiamo è isolare il più possibile. I container è un processo completamente isolato e su linux questo è possibile. Un container è un albero di processi con privilegi molto limitati che non ha accesso completo di risorse e pensa di essere unico nel sistema. 
Abbiamo alcune cose a cui pensare: 
- Isolare il file system: Funzionalità chtroot
- Isolare CPU e memoria: cgroup 
	- limita CPU, memoria, I/O e rete
- Isolare i namespace: usare Namespace 
	- non vede processi, rete, I/O, User/Group
Tutto questo è quello che accade, ma attualmente abbiamo quello che è il Container engine. [[Docker]] è lo standard attualmente. Ci permette di creare un container partendo da un'immagine. Un container possiamo anche definirlo come un'immagine in esecuzione. Possiamo anche scaricare immagini su Docker Hub. Ogni container ha un indirizzo ip in una rete virtuale.


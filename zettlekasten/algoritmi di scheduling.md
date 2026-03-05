Gli algoritmi di [[Scheduling processi]] sono: 
- First-come first served 
	- molto male 
- shortest-job first served 
	- va bene ma non sappiamo se il processo dura poco o tanto
- round robin
	- divido il turno in modo semplice 
	- funziona ma non priorità 
- priority scheduling 
	- problema è che quelli con bassa priorità non riesce a fare
- Multi-level queue scheduling 
	- sappiamo che noi andiamo a fare, poco alla volta, quelle cose che hanno una priorità minore.
	- questo è il metodo migliore

In [[Linux]] abbiamo completely fair scheduler dove abbiamo 6 livelli. Le operazioni importanti vengono effettuati il più possibile mentre quelle con bassa priorità (batch) sono abbastanza lenti. In media tutti i programmi finiscono nel adder che è una priorità media.
Per cambiare la priorità `nice(2) getpriority(2)...`
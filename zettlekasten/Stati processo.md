[[Processi e thread]]
## Definizione 
I processi funzionano in stati che vanno gestiti dal [[Sistema Operativo]].
Gli stati sono: 
- [[Creazione processi]]
- ready
	- quando sono pronti per funzionare
- running (D) 
	- qui possiamo o andare in ready oppure waiting 
- waiting (interruptible sleep S)
	- qua in media è posizionato in input output 
	- bisogna aspettare più tempo per il processo 
	- da qua si parte in ready
- Ininterruptable sleep (D)
	- qui lo sleep non può essere interrotto
	- nella maggior parte dei casi sta facendo IO 
- Stopped (T)
	- bloccato 
	- Using sigstop o sigtstp  signals possiamo andare a fare uno stop [[Segnali in linux]]
- Zombie (Z)
	- Processo che ha perso il padre. 
### Correlati 
- [[Loader, librerie e pagine condivise]] (per la creazione e avvio del processo)
- [[Collo di bottiglia processi]]
- 
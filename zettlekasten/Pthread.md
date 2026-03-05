[[Thread]]
## Definizione
per la manipolazione dei thread abbiamo pthread che è una libreria.
ogni thread ha un thread id, un suo stack e metadati. 

Per usare pthread dobbiamo includere pthread.h e per compilare dobbiamo inserire `gcc MyProgram.c -0 MyProgram -lpthread

le funzione principali sono: 
- iniziare
	- int pthread_create(pthread_t *thread, const pthread_attr_t      *attr, void *(*start) (void *), void *arg);
	- in caso di successo è 0 
	- internamente crea un thread con `clone()
		- simile alla fork ma è molto complessa 
		- crea processo figlio 
- ammazzare
	- possiamo suicidarsi con pthread_exit()
		- come argomento un void 
	- assassinato da pthread_cancel(pthread_t thread)
		- qua possiamo ammazzare chiunque 
	- il processo finisce e quindi tutti i figli muoiono
- aspettare 
	- pthread_join(pthread_t thread, void ** retval);
		- il doppio ** è puntatore a puntatore a join 
		- questa funziona come la wait 
		- ogni thread deve avere una join
			- altrimenti diventa zombie 
			- qua spacchiamo tutto se non si aspetta
		- possiamo creare funzione pthread_detach 
			- in questo caso va sempre in background ma nah
		- questa è sempre bloccante e tutti la possono usare 
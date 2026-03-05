[[Linux]]
## Definizione 
ricordiamo [[Permessi Linux]] e [[Utenti e gruppi in linux]]. 

Oltre ai 3x3 permessi abbiamo anche 3 globali: 
- Set user ID (suid)
	- alcuni processi non sono eseguibili anche con tutti i permessi.
	- suid bit posso andare ad eseguire sempre con [[Utente root]] 
- set group ID (guid)
	- al assegnare questo bit -G- allora tutti possono accedere 
	- la cartella sarà di proprietà del gruppo della cartella madre
- sticky bit 
	- sempre in ambito di cartelle 
	- quando noi creiamo un file nella cartella con sticky bit nessuno può cancellare file di altri proprietari e gruppi

ricordiamo che i [[Link (hard & soft)]] e come i soft non hanno permessi mentre quelli hard hanno un link nel [[Inode]]. 

### Correlati 
- [[Comandi permessi Linux]]  
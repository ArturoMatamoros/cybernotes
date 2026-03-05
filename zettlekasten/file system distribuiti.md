[[Problematiche dischi]]
## Definizione 
Nell'utilizzo di sistemi molto grandi noi andiamo a parlare di file system distribuiti. Questi sono quello che ci permettono di utilizzare un insieme di [[File system]] in contemporanea. 

un file system distribuito è un file system che risiede in dischi e macchine diverse e ha bisogno di: 
- orchestratore (software) 
	- questo permette di avere un enorme file system affidabile 
	- questo software è estremamente complesso 
	- sono affidabili, buone prestazioni e 
- questi sistemi girano in un cluster a cui gli utenti si connettono
	- qua ho metadata server (come [[Inode]]) 
	- data server (dischi nei quali sono contenuti i blocchi)

I file system più utilizzata è:
- Hadoop per big data 
	- funziona come abbiamo descritto ma ha tanti problemi
- CEPH
	- possiamo avere fs distribuito 
	- può funzionare anche dispositivi a blocchi 
	- questo è versatile ed è quello che il prof vede nel futuro

### Correlati 
- [[file system di Rete]]

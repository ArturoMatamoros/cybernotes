[[Structured Query Language (SQL)]] 
I [[Database relazionali]] alla creazione sono strutturati in questo modo: 
- Information_schema 
	- questo è un database che ha tutti i metadati 
	- Questo, se attaccato, può permetterti di comprendere la struttura del database
- "database creato da noi"
- mysql
	- Questo è il database più importante e contiene l'accesso a tutti i database presenti
	- Questo è il database più importante e quindi quello che più di tutti deve essere protetto da [[SQL Injection]] e attacchi vari. 
- Performance_schema 
	- Grafana e prometeos è un sistema di monitoraggio che vanno a monitorare le prestazioni, quanto è utilizzato e orari di utilizzo. 
	- Questo è utile in quanto possiamo scegliere quando attaccare e dove. 



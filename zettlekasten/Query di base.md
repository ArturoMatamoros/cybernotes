[[Query]]
Ci sono dei comandi di base per Database e questi sono in [[Structured Query Language (SQL)]].
- CREATE DATABASE nome_database;
- USE nome_database;
- SHOW DATABASES; 
	- vedere tutti i database presenti sul server7
	- Show ha diverse opzioni 
- DROP DATABASE nome-database;
	- Eliminazione del database
- "query..." IF EXISTS;
	- Questo, dopo un comando, ci assicura di non generare output. 
	- Questo è importante in caso di attacchi [[Attacco Brute force]]
- mysql -u root
	- efettuare accesso root
- mysql -u nome_utente -pLamiapassword
- mysql -u nome-utente -p nome-del-database
- mysql -h host -P porta -u nome-utente -p 
- NULL/NOTNULL ci permetti di non inserire i campi nuovi.
	- IS NULL/IS NOT NULL sono dei booleani e va usato dopo where
- 
Link:
- [[Query uso tabelle]]
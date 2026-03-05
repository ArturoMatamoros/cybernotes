La SQL Injection è una tecnica di attacco che consiste nell'atto di iniettare all'interno di un input dei pezzi di codice [[Structured Query Language (SQL)]] che vengono poi letti come tali dal programma andando a cambiare così il comportamento della [[Query]].  Esempi sono nella fase di registrazione.  Grazie a questo noi possiamo andare a: 
- [[Dump]]
- modificare dati / tabelle 
- bypassare autenticazioni
- eseguire comandi DB avanzati

Alcuni modi di proteggere è [[Query parametrizzate]], attenta sanitizzazione dei dati ecc. 

Un modo di proteggersi è attraverso il middleware, quindi andare a vedere anche [[Containerizzazione di database]]. [[Database relazionali]] [[Vulnerabilità database]] 

Per evitare di esporre il database al front-end noi utilizzare middleware. Questo si dedica attraverso API e quindi andiamo ad evitare la connessione diretta. Qui è dove noi andiamo ad effettuare il nostro attacco. 

Link:
- [[Struttura Databases e criticità]]
- [[Come effettuare una SQL injection]]
- [[Tipi di SQL injection]]
- [[SQLi di secondo ordine]]
- [[SQLi per tipo di database]]
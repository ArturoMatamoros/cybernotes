le [[SQL Injection]] sono di due ordini: 
- di primo ordine
	- dove noi andiamo ad inserire i dati direttamente nel database 
	- Questo è quello che andiamo a vedere per esempio quando vediamo il metodo classico di [[Come effettuare una SQL injection]]
- di secondo ordine
	- dove gli sviluppatori cercano di proteggersi dalla injection creando un database dove vengono inseriti i dati che noi andiamo ad immettere. Da qui nessuna vulnerabilità è stata rilevata. Al utilizzare una differente richiesta la applicazione riprende i dati precedentemente salvati e li utilizza all'interno del vero database. 

Quelli di secondo ordine è il risultato di un tentativo di eliminazione del pericolo ma questo non fa altro che aggiungere un layer di sicurezza in più che non è abbastanza per una persona che conosce questo meccanismo. 
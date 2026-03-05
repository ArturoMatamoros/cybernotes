[[Query]]
Una volta inseriti i dati noi vogliamo andare ad inserire

	SELECT idUtente, COUNT(*) AS numero_ordini 
	FROM ordini
	GROUP BY idUtente

Se al posto del ID noi vogliamo andare a vedere le info 

	SELECT o.id AS id_ordine,
		u.nome,
		u.cognome,
		o.dataOra,
		o.importo,
		o.descrizione
	FROM ordini o
	JOIN utenti u ON o.idUtente=u.id;

La union invece funziona così:

`SELECT a, b FROM table1 UNION SELECT c, d FROM table2`

Attenzione che per fare in modo che funzioni devi:
- richiedere lo stesso numero di informazioni 
- i tipi di dati devono essere compatibili 

LINK: 
- [[SQLi Union attacks]] 
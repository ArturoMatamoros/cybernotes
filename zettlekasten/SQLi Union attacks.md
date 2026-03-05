questo fa parte dei [[Tipi di SQL injection]] e sfrutta [[Query per unione tabelle]]. Quando ci troviamo in uno scenario dove siamo all'interno di un SELECT noi possiamo bypassare il tutto attraverso union. 

All'interno di :
`SELECT name, description FROM products WHERE category = 'Gifts'`
noi possiamo inserire 
`' UNION SELECT username, password FROM users--`

Questi andrebbe ad effettuare un SELECT di ciò che noi vogliamo 

Qui però abbiamo un problema: la conoscenza di quello che sono le tabelle e i nomi esatti. Per questo io consiglio di andare ad analizzare come sempre [[SQLi per tipo di database]]. 

Abbiamo i problemi collegati al funzionamento di una union e risolviamo con: 
- [[Determinare numero di colonne SQLi union]]
- [[Determinare tipo di data nelle colonne SQLi union]]
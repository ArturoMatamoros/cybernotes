[[Bash e Shell]]
Tar è un comando che serve per andare a creare delle compressioni di file. 
Possiamo estrarre e comprimere archivi grazie ad una serie di flag. 
Le parole chiavi sono 
- c, x, f, t
	- create, espandere, file e take a look 
- utilizziamo due algoritmi z (più veloce) j (più efficente)

Alcuni esempi sono: 
- tar cvfz backup.tar.gz /etc 
- tar cvf backup.tar.gz -C /tmp
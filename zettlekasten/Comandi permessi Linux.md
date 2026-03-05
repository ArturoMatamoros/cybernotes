[[Permessi Linux]]
## I comandi importanti 
Nei [[Comandi File system]] abbiamo `ls -l` ci da tutte le info.
come sempre segue la [[Struttura dei comandi in Linux]]

per modificare i permessi di un file usiamo `chmod[-r]<permessi><file>` per dare quali sono i permessi che voglio cambiare ci sono vari modi: 
- Assoluto: siccome abbiamo 3 bit possiamo usare un numero da 0-7
- Mirato: stringa 3 punti
	- utenti
	- +/-
	- r, w, x

per modificare il proprietario abbiamo: 
- `chown utente file`
- `chown gruppo file`
- `chown utente:gruppo file`

per una lista più completa comprendendo [[Utenti e gruppi in linux]] abbiamo [[Comandi utenti]] 

Per quanto riguarda i [[Permessi speciali (SUID, SGID, Sticky bit)]] rappresentiamo I bit particolari al posto della x e quando usiamo chmod usiamo 3 bit extra 
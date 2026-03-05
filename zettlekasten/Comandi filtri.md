[[Bash e Shell]]
## Definizione
Questa è una lista di comandi [[Linux]] che ci permette di andare a filtrare file o altro e sono fondamentali quando si usa [[Pipe and Redirect]]. I comandi più importanti sono: 
- `grep [options] pattern [file...]` : Questo ci permette di cercare un pattern in un file e stampare in base alle opzioni 
	- • —n: stampa il numero di riga
	-  -i : case insensitive
	-  -c : stampa il numero di match
	-  -v : stampa solo le linee che non contengono il pattern
- `cut` questo ci permette di tagliare una parte specifica del file 
	- byte con `-b byte
	- un campo dato un separatore `-d separatore -f campo
- `tr[-cds][set1][set2]` : cambia (in base all'opzione) i caratteri desiderati
- `sort[-dfnru][-o outfile] [file...]`: classico sort, ha tante opzioni
	- `-n` : ordine numerico 
- `uniq[-cdu]`controlla se le linee sono duplicate e le elimina
	- `-c` : quante righe ci sono corrispondenti
- `wc[-lwc][file]`: conta linee (l), parole(w) e caratteri (c) dello stdin o del file

 per comprendere queste al meglio impara le [[Bash Expansions]], specialmente per grep

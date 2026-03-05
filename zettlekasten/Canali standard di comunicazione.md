[[Bash e Shell]]
## Definizione 
I tre canali standard di comunicazione in [[Linux]] sono:
- `stdin` che legge attraverso la tastiera per default 
	- Questo viene sempre identificato con 0
	- < redirige st input
- `stdout`che stampa sullo schermo 
	- Identificato con 1
	- > redirige st output 
- `stderr` che stampa anche esso su schermo
	- Identificato con 2
	- 2> redirige st di errore
conoscere questo ci permette di utilizzare il [[Pipe and Redirect]] nel nostro [[Script Bash]].

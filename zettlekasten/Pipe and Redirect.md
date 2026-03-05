[[Bash e Shell]]
## Definizione 
pipe and redirect sono operazioni fondamentali nella creazione di [[Script Bash]] in linguaggio [[Bash e Shell]] nelle quali noi possiamo manipolare i [[Canali standard di comunicazione]] in modo tale da potere usare file come Input/output (Redirect) oppure dare come input di un primo comando l'output del secondo (Pipe) 
## Comandi di Redirect 
parzialmente visti in [[Struttura dei comandi in Linux]] possiamo approfondire con definire il redirect (stampa su un file) sovrascrivendo il risultato
- `>`e `2>` per stdin e stderr
e il Append(dove aggiungiamo alla coda)
- `>>`e `2>>` per stdin e stderr
Abbiamo anche il caso in cui vogliamo entambi
- &> e &>> dove buttiamo dentro al file a priori

allo stesso modo funziona per lo standard in da file `<

## Comandi di Pipe
segue la struttura `comando1 | comando2` e possiamo usare il comando come variabile con `$(comando)` 

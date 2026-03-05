[[Processi e thread]]
## Definizione 
lo scheduling è il l'atto che lo scheduler del [[Sistema Operativo]] effettua per andare a scegliere il processo più adatto da gestire tenendo conto di vari fattori tra cui gli [[Stati processo]]

Fondamentale è capire come organizzare processi cpu, I/O bound.
Lo scheduler opera con un algoritmo per organizzare tutto, Il context switching è il metodo on cui lo facciamo.
- salva lo stato 
- carica un nuovo processo caricato con stato precedente 
Il context switching è molto a basso livello su assembly. 

Il Yield è uno strumento che da precedenza ad altri processi andando nello stato di ready automaticamente 

Gli [[algoritmi di scheduling]] sono:


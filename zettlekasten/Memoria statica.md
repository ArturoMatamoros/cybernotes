[[Memoria nei sistemi operativi]]
## Definizione 
la memoria statica è una porzione di memoria che viene allocata e data sin dalla compilazione del programma, esse non possono essere modificate durante il runtime.
## Limiti della memoria statica 
le variabili globali quando sono inizializzate senza info vengono poste a 0 ma se queste sono di funzione e non vengono dichiarate loro contengono i dati contenuti nel vecchio spazio di memoria.

non possiamo creare un array di lunghezza non nota. Posso fare il sovradimensionamento, questo è più sicuro della [[Memoria dinamica]] ma spende tanto spazio in memoria. 
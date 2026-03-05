[[Dischi e file system]]
## Definizione 
introdotto come metodo di [[Allocazione blocchi nel disco]], è una struttura dato che rappresenta un nodo o cartella. Questo è un concetto fondamentale del [[File system Linux]]

Ogni nodo hanno un Inode number e questi tanti sono finiti e numerabile, una volta superato il limite non è possibile creare file.

Nel disco abbiamo partizione e abbiamo qualche blocco dove abbiamo un vettore di inode. 

8ogni inode potrebbe essere diretto ad un data block oppure una cartella, una cartella è un file e non fa altro che una tabella che contiene altri inode. 

Il nome del file non è contenuto nei metadati.

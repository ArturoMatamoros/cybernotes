[[File system Linux]]
## Lista di comandi e opzioni principali
Questi sono fondamentali per utilizzare il [[File system]] con il terminale e segue sempre la [[Struttura dei comandi in Linux]].
- `ls[opzioni][dir]` : lista contenuto dir  
	- le opzioni fondamentali sono:
		- `-l` long (elenco e altri dettagli)
		- `-a` mostra tutti i file, anche nascosti
- `rm[-rfi][filename]` : rimuove file 
	- opzioni importanti:
		- `-r` rimuove tutti i file in una cartella 
		- `-f` rimuove ogni dato senza chiedere conferma
		- `-i` con questo richiede conferma
- `cd` : change directory 
- `mkdir` : crea sub-directory
- `rmdir` : rimuove sub-directory se vuota
- `cp<file1><file2>` copia `mv<file1><file2>`sposta
	- opzioni principali:
		- `-r` : usa ricorsione   
		- `-f` : non chiede conferma
		- `-i` : chiede conferma 
- `ln[-s]<sorgente><destinazione>` : creazione di [[Link (hard & soft)]]
- `find[path][-n nome][-print]` : ricerca di file e stampa path
- `cat <file>` : stampa contenuto file 
- `touch <file>` : crea file 
- `less <file>` : apre visualizzatore 
- `head` e `tail` : mostra prima e ultime righe file
- ci sono vari tipo di editor di testo 
- `tee lista.txt`: stampa sia sul documento sia sullo schermo
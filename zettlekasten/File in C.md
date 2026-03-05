[[Programmazione in C]]
## Definizione 
in C il modo in cui accedere a file è simile al modo in cui si fa [[Comandi File system]] dato che si lavora con system calls su linux. 

Ci sono 3 fasi nel lavorare con il file: aprire, leggere/scrivere, chiudere.
- Aprire 
	- utilizzare fopen(path,modo)
	- controllare sempre se è andato a buon fine 
		- controllare se file != null
- Leggere/scrivere
	- leggere
		- fgetc(file) 
		- fgets(buffer, N, file) 
	- scrivere 
		- fputc(carattere,file)
		- fputs(stringa,file)

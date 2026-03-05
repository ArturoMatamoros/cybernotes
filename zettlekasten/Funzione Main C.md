[[Programmazione in C]]
## Definizione 
Ogni programma che viene chiamato deve avere una funzione main. Questa funzione non è altro che la funzione che parte in automatico al chiamare un programma dal terminale.

in linguaggio C la main ha questo aspetto:
```C
int main(int argc, char *argv[])
{
	printf("hello world\n");
	return 0;
}
```
ricordiamo che ogni programma deve restituire un intero che dice alla funzione padre se il programma è andato a buon fine o no. Lo 0 significa che tutto procede in modo corretto.

### Correlati 
[[Funzioni in programmazione]]
[[Programmazione in C]]
[[Error handling]]

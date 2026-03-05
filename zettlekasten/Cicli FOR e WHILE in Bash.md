[[Bash e Shell]] 
## Struttura FOR
la struttura del [[Cicli in programmazione]] for è della seguente forma:
```bash
for ((Inizializzazione; test; step))
do 
	[Comands]
done
```
## Struttura WHILE 
quando parliamo del while abbiamo anche `until` che funziona come un while ma fino. 
``` bash
n=0
while ((n<=4))
do 
	((n=n+1))
	echo $n
done

until ((n>=2))
do
((n=n-1))
done
```
### Correlati 
[[Bash e Shell]]

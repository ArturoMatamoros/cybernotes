[[Bash e Shell]]
## Struttura delle operazioni condizionali in bash 
la [[Struttura condizionale]] in [[Bash e Shell]] è la classica: 
```bash 
	if (condizione) then 
		ramo1
	elif (condizione2) then
		ramo2 
	else 
		ramo3
	fi
```
queste possono essere tra numeri (sono le classiche che conosco già) e ci sono anche quelle tra stringhe e quelle tra file 

## Confronto tra stringhe

Strutture di controllo Condizioni tra stringhe
Si utilizza la sintassi  `[[espressione]]
Gli operatori di confronto sono:
•= !=: uguaglianza o differenza
• > < : ordinamento alfabetico
• -z : vero se la stringa è vuota (o la variabile non è definita).
! -z è vero se la variabile non è vuota
• E' necessario usare l'operatore $ e mettere spazi tra
operandi
Esempio: if `[[ $a != $b 1]]
Esempio: if `[[ ! -z $var 1]]` : vero se var esiste e non
è vuota

## Confronto tra file

E' molto semplice testare se un file esiste, è vuoto o è una
cartella, usando una condizione if Il ... 11 con:
• -a path : vero se path esiste
• -f path : vero se path è un file
• -d path : vero se path è una cartella
• -s path: vero se path non è vuoto
• -r path : vero se posso leggere path
• —w path : vero se scrivere leggere path
• -x path : vero se eseguire/attraversare leggere path

### correlati
[[Operatore logici in bash]]
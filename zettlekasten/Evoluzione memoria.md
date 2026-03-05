[[Memoria nei sistemi operativi]]
## Storia 
all'inizio non esistevano i SO e il programma aveva il pieno controllo.
### Meccanismo a sostituzione totale 
il SO sostituisce completamente la memoria nel disco. 
- funziona 
- lento
- non adatto a multi tasking
### Base e limit 
- ogni processo ha una base e limite 
- qua nasce la [[Memoria virtuale]].
- risolviamo isolamento processi 
- il problema è che la allocazione contigua
### Memoria segmentata
- ogni processo è segmentato e come la base limit dopo
- la MMU è uguale ma con base e limit in una tabella
- usata molto negli anno 80, molto veloce 
- problemi, segmenti di lunghezza diversa e frammentazione 
### Paginazione 
- dividiamo tutto nella stessa dimensione 
- la MMU usa una tabella di pagine. [[Paginazione]]
- la memoria virtuale è molto grande, più della fisica
- difetti: MMU potente, la tabella è tanto grande ed è standard
- se la memoria fisica è piena allora noi andiamo a salvare sul disco le pagine meno utilizzate.


[[Evoluzione]]
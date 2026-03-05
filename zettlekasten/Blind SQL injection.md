questo fa parte dei [[Tipi di SQL injection]] ed è quello che è ora il più comune ma anche più complicato.  Questo tipo di attacco infatti non ritorna risultati o dettagli di errori. Questo può essere usato per accedere a dati non autorizzati. 

Le tecniche fondamentali sono: 
- possiamo inserire un errore che abbia un qualche ripercussione. Questo si può fare attraverso una condizione in una logica booleana oppure andare a condizionare una divisione per zero
- Possiamo creare un delay nella processazione della query. Questo ti fa capire la verità dietro la logica basata su quanto tempo ci mette a rispondere. 
- puoi provocare un interazione network out of band, usando [[Tecniche OAST]]. Questa è una tecnica molto potente. Puoi dopo estrarre dati dal canale out-of-band. esempio andando a inserire i dati in un DNS lookup per un dominio da te controllato. 

Cosa possiamo fare ?
- [[Boolean blind SQLi]]
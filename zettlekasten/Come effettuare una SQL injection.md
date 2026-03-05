[[SQL Injection]] 

`$query = "SELECT * FROM users WHERE username ='$su AND password='$p'";`

Data questa query noi comprendiamo come andare a modificare questa in modo tale da andare a capire come modificarla. 

Il modo più emblematico è quello di inserire ' OR '1'='1' all'interno. Oppure inserire commenti in modo tale che il codice non venga più letto dalla macchina. Il nostro codice diventa quindi 

`$query = "SELECT * FROM users WHERE username ='' AND password='' OR '1'='1';`

Questo è il metodo più classico di andare a fare una injection. 

LINK: 

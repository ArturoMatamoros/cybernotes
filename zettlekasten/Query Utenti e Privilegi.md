Quando parliamo di [[Database]] le autorizzazioni sono chiamate PRIVILEGI. 
I comandi sono: 
'nome_utente'@'ip_client/dns' password
I permessi possono essere dati per ogni singola funzione. Queste possono essere date sia dal livello database e sia a tabella.  Queste vengono conservate all'interno del database mysql che troviamo in [[Struttura Databases e criticità]].

Per creare l'utente:
CREATE USER 'mario'@'localhost' IDENTIFIED BY 'Password';
CREATE USER 'mario'@'192.168.1.2' IDENTIFIED BY 'Password';
CREATE USER 'mario'@'192.168.1.3' IDENTIFIED BY 'Password';
CREATE USER 'mario'@'192.168.10.%' IDENTIFIED BY 'Password';

Per garantire un privilegio: 
GRANT SELECT ON scuola.* TO 'mario'@'localhost';  

abbiamo delle variazioni: 

GRANT SELECT ON * .* TO 'mario'@'localhost';  
- per garantire l'accesso completo
GRANT SELECT ON scuola.* TO 'mario'@%;
- per far si che l'accesso sia disponibile anche fuori dal local host

GRANT ALL PRIVILEGES ON scuola.* TO 'mario'@'localhost';

GRANT SELECT,INSERT,UPDATE ON scuola.* TO 'docente'@% WITH GRANT OPTION;
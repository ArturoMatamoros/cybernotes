[[Initial Windows server and client settings]]
1. Accedi alla macchina Server2019 con le credenziali di amministratore locale.
2. Premi Windows + R, scrivi ncpa.cpl e premi Invio. (Si aprirà la finestra Network
Connections).
3. Fai clic destro sulla scheda di rete (es. Ethernet) -> Properties.
4. Seleziona Internet Protocol Version 4 (TCP/IPv4) e clicca sul pulsante Properties.
5. Seleziona l'opzione Use the following IP address e compila così:
○ IP address: 10.0.0.3
○ Subnet mask: 255.255.255.0 (si compilerà in automatico cliccandoci)
○ Default gateway: 10.0.0.2
6. Sotto, l'opzione Use the following DNS server addresses si attiverà. Inserisci:
○ Preferred DNS server: 10.0.0.3
7. Clicca OK, poi Close.
8. Disattivazione Firewall: Apri il Server Manager (solitamente si apre da solo, altrimenti
cercalo nel menu Start).
9. Nella colonna di sinistra, clicca su Local Server.

10. Nel pannello centrale (Properties), individua la voce Windows Defender Firewall e clicca
sulla scritta blu a fianco (probabilmente ci sarà scritto Public: On).
17. Si aprirà la finestra del firewall. Nella colonna di sinistra, clicca su Turn Windows Defender
Firewall on or off.
18. Seleziona il pallino Turn off Windows Defender Firewall (not recommended) per tutte le
reti visualizzate (Domain, Private, e Public network settings). Clicca OK e chiudi la finestra
del firewall.
19. Cambio Nome: apri il menu Start -> clicca sull'icona dell'ingranaggio (Settings) -> System
-> About (in fondo a sinistra).
20. Scorri verso il basso o guarda a destra e clicca su Rename this PC (oppure su Advanced
system settings -> tab Computer Name -> Change...).
21. Nel campo cancella quello vecchio e scrivi DCPRETEST.
22. Clicca Next, ti chiederà di riavviare. Clicca Restart now.
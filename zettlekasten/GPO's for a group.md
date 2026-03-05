[[Group Policies (GPO)]]
1. Apri Start -> cartella Windows Administrative Tools -> Group Policy Management.
2. Sulla sinistra, espandi l'albero: Forest: its.pri -> Domains -> its.pri -> espandi
UFFICIO.
3. Fai clic destro sulla cartella UTENTI UFFICIO e seleziona Create a GPO in this domain,
and Link it here....
4. Name: scrivi Restrizioni Ufficio e clicca OK.
5. Espandi "UTENTI UFFICIO", fai clic destro sulla GPO appena creata ("Restrizioni Ufficio") e
scegli Edit.... Si aprirà il Group Policy Management Editor.
6. Le policy richieste sono per l'utente. Naviga in: User Configuration -> Policies ->
Administrative Templates.
7. Pannello di controllo: Clicca sulla cartella Control Panel. A destra, fai doppio clic su
Prohibit access to Control Panel and PC settings. Metti il pallino su Enabled, clicca
Apply e poi OK.
8. Desktop: A sinistra espandi Desktop e cliccaci. A destra, doppio clic su Hide and disable
all items on the desktop. Seleziona Enabled, Apply, OK.
9. Menu Start: A sinistra clicca su Start Menu and Taskbar. A destra, cerca Remove Run
menu from Start Menu, doppio clic, seleziona Enabled, Apply, OK.
10. Installazione applicazioni: A sinistra, torna su Control Panel -> clicca su Programs. A
destra, doppio clic su Hide "Programs and Features" page, seleziona Enabled, Apply, OK.
11. Chiudi la finestra dell'Editor (la x in alto a destra).
[[Active directory]]

2. Accedi a DCPRETEST. Si aprirà in automatico il Server Manager.

3. Nel Server Manager, clicca su Add roles and features (al centro dello schermo).
4. Clicca Next per 3 volte di fila fino alla schermata "Server Roles".
5. Spunta la casella Active Directory Domain Services. Si aprirà una finestrella, clicca su
Add Features.
6. Spunta anche la casella DNS Server. Clicca su Add Features nella finestrella.
7. Clicca Next per tutte le finestre successive e infine su Install.
8. Attendi la fine dell'installazione. Al termine, clicca sul link in azzurro nella finestra: Promote
this server to a domain controller.
9. Si apre una nuova procedura guidata. Seleziona Add a new forest (la terza opzione).
10. Nel campo "Root domain name:" digita ITS.PRI e clicca su Next.
11. Inserisci la password per il DSRM (Vmware1!) in entrambi i campi. Clicca Next.
12. Ignora l'avviso sulla delega DNS e clicca Next.
13. Il NetBIOS domain name (ITS) verrà generato da solo. Clicca Next.
14. Lascia i percorsi predefiniti, clicca Next, poi ancora Next.
15. Attendi il controllo dei prerequisiti (comparirà una spunta verde con la scritta All
prerequisite checks passed successfully) e clicca su Install.
16. Il server farà tutto da solo e si riavvierà automaticamente.
17. Al riavvio, accedi con le credenziali ITS\Administrator.
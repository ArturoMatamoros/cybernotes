[[Roaming profiles and Home directory]]
1. Apri dal menu start Active Directory Users and Computers.
2. Vai nella OU UFFICIO -> UTENTI UFFICIO.
3. Tieni premuto il tasto CTRL sulla tastiera e clicca una volta su Utente1 e una volta su
Utente2 per evidenziarli entrambi.
4. Fai clic destro su uno dei due evidenziati -> Properties.
5. Vai alla scheda Profile.
6. Metti la spunta su Profile path: e scrivi il seguente percorso di rete:
\\DCPRETEST\PROFILIUFFICIO\%username%
7. Metti la spunta in basso, nella sezione "Home folder", su Connect:.
8. Scegli una lettera (es. Z:), e nel campo "To:" inserisci il percorso della cartella documenti:
\\DCPRETEST\DOCUMENTI UFFICIO\%username%
9. Clicca su Apply e poi su OK.
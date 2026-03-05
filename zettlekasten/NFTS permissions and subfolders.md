[[File server and sharing]]
1. Apri File Explorer (l'icona della cartella gialla in basso), vai in This PC -> Local Disk (C:) ->
apri la cartella DOCUMENTI UFFICIO.
2. Tasto destro in uno spazio vuoto -> New -> Folder. Creane due: DOCUMENTI
TEMPORANEI e DOCUMENTI PUBBLICI.
3. DOCUMENTI TEMPORANEI (Lettura/scrittura a tutti gli utenti):
○ Fai clic destro su DOCUMENTI TEMPORANEI -> Properties -> scheda Security ->
pulsante Advanced.
○ Clicca in basso su Disable inheritance. Scegli la prima opzione: "Convert inherited
permissions into explicit permissions on this object".
○ Nell'elenco, rimuovi eventuali utenti specifici (Seleziona Users e premi Remove,
lascia System e Administrators). Clicca in alto su Add, poi sul link testuale Select a
principal.
○ Digita Domain Users, fai clic su "Check Names" e premi OK.
○ Sotto "Basic permissions", spunta Modify (che abiliterà anche Write e Read). Clicca
OK, poi Apply e OK su tutte le finestre.
4. DOCUMENTI PUBBLICI (Lettura a tutti, Admin Full Control):
○ Fai clic destro su DOCUMENTI PUBBLICI -> Properties -> scheda Security ->
pulsante Advanced.
○ Clicca su Disable inheritance -> Convert....
○ Rimuovi il gruppo generico "Users".
○ Clicca Add -> Select a principal -> digita Domain Users -> OK. Lascia spuntato
solo Read & execute, List folder contents, Read. Clicca OK.
○ Gli "Administrators" avranno già Full control. Premi OK su tutte le finestre.
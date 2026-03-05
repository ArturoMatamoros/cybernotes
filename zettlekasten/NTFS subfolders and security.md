[[Roaming profiles and Home directory]]
1. In C:\DOCUMENTITS crea 5 cartelle: DATICOMUNI, DATIUT1, DATIUT2, DATIBACKUP, DEPOSITO SOFTWARE.
2. DATICOMUNI: Clic destro -> Properties -> Security -> Advanced. Disable inheritance -> Convert. Rimuovi Users. Add -> Domain Users -> spunta Modify (che include Write/Read). OK.
3. DATIUT1: Clic destro -> Security -> Advanced. Disable inheritance -> Convert. Rimuovi Users. Add -> Utente1Uff -> spunta Full Control. OK.
4. DATIUT2: Clic destro -> Security -> Advanced. Disable inheritance -> Convert. Rimuovi Users. Add -> Utente2Uff -> spunta Full Control. OK.
5. DATIBACKUP: Clic destro -> Security -> Advanced. Disable inheritance -> Convert. Rimuovi Users. Add -> UtenteBACK -> spunta Full Control. OK.
6. DEPOSITO SOFTWARE: Clic destro -> Security -> Advanced. Disable inheritance -> Convert. Rimuovi Users. Add -> REPARTO IT -> spunta Full Control. OK.
### 18. Hard Quota 5GB
1. Apri Start -> Windows Administrative Tools -> File Server Resource Manager.
2. Espandi Quota Management -> clic destro su Quotas -> Create Quota....
3. Path: sfoglia e seleziona C:\DOCUMENTITS.
4. Sotto Derive properties from... seleziona il pallino Define custom quota properties -> clicca Custom Properties....
5. Space limit: 5 e scegli GB. Seleziona Hard quota. OK e Create (salva senza template).
### 19. Map Network Drive sul Client
1. Vai su CLIENTDOLC (accedi come Utente1Uff).
2. Apri File Explorer -> This PC.
3. In alto nel menu clicca su Computer -> Map network drive.
4. Scegli una lettera, scrivi \\DCDOLC\DOCUMENTITS e clicca Finish.
5. Fai log out, accedi come Utente2Uff e ripeti i passi 2-4.
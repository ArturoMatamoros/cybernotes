Phase 7: [[Windows OS]]

1. Server Manager -> Add roles and features -> vai a Features -> spunta Windows Server Backup. Installa.
    
2. In C:\ crea la cartella BACKUPGIORNALIERI.
    
3. Apri Windows Server Backup (da Tools).
    
4. A destra clicca Backup Schedule.... Next.
    
5. Seleziona Custom -> Next. Clicca Add Items -> espandi C: e spunta DOCUMENTITS. OK, Next.
    
6. Scegli More than once a day: aggiungi le ore 12:00 PM e 8:00 PM (20:00). Next.
    
7. Seleziona Back up to a volume -> Next. Scegli il volume C: (oppure Back up to a shared network folder e usa \\DCDOLC\c$ \BACKUPGIORNALIERI). (Nota: Windows Server Backup preferisce dischi dedicati. Se dà errore sul volume C:, scegli l'opzione "Shared network folder" e usa \\DCDOLC\c$\BACKUPGIORNALIERI). Finish.
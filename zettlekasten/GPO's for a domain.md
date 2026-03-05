[[Group Policies (GPO)]]
1. Sempre in "Group Policy Management", fai clic destro sul dominio radice, cioè su its.pri
(l'icona con il dominio, sotto la cartella "Domains").
2. Seleziona Create a GPO in this domain, and Link it here....
3. Name: NOTASKMANAGER, clicca OK.
4. Fai clic destro sulla nuova GPO "NOTASKMANAGER" sotto il dominio e seleziona Edit....
5. Naviga in: User Configuration -> Policies -> Administrative Templates -> System ->
Ctrl+Alt+Del Options.
6. A destra, fai doppio clic su Remove Task Manager.
7. Seleziona Enabled, clicca Apply e poi OK. Chiudi l'editor.
8. Torna sul server, apri il menu start, scrivi cmd, premi invio e digita gpupdate /force per
applicare subito le policy.
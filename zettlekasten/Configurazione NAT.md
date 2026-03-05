### [[Processo configurazione network]]
Il NAT serve a permettere ai computer di una rete locale (con IP privati, es. 10.0.0.x) di uscire su Internet usando un indirizzo IP pubblico (es. 50.0.0.x). In questo caso specifico, configuriamo il **PAT (Overload)**, che permette a molti host interni di usare un solo IP pubblico contemporaneamente.
### Passaggio 1: Definire la Rotta di Uscita (Default Route)
Il router deve sapere dove mandare il traffico destinato a Internet. Lo mandiamo all'ISP (Internet Service Provider).
- **Comando:** ip route 0.0.0.0 0.0.0.0 IP_ISP
- **Nel tuo caso:** ip route 0.0.0.0 0.0.0.0 50.0.0.2
- Significato: "Qualsiasi traffico non locale (0.0.0.0 0.0.0.0), spediscilo all'indirizzo del router dell'operatore (50.0.0.2)".

---

### Passaggio 2: Identificare le Interfacce (Inside vs Outside)
Dobbiamo dire al router quale porta guarda verso i nostri PC e quale guarda verso Internet.
1. **Entra nell'interfaccia locale (LAN):**
    - interface f0/0 (o quella collegata allo switch interno)
    - ip nat inside
2. **Entra nell'interfaccia esterna (WAN):**
    - interface f0/1 (o quella collegata verso l'ISP)
    - ip nat outside
3. exit

---
### Passaggio 3: Creare il Pool di IP Pubblici
Dobbiamo definire quale IP pubblico useremo per "mascherare" i nostri PC.
- **Comando:** ip nat pool NOME_POOL IP_INIZIO IP_FINE netmask MASCHERA
- **Nel tuo caso:** ip nat pool INTERNET 50.0.0.1 50.0.0.1 netmask 255.0.0.0
- Nota: Se metti lo stesso IP all'inizio e alla fine (50.0.0.1), stai usando un solo IP pubblico per tutti.

---
### Passaggio 4: Creare la ACL (Access Control List)
La ACL decide **chi** ha il permesso di uscire su Internet. Senza questo passaggio, il NAT non sa chi deve tradurre.

- **Comando:** access-list NUMERO permit host IP_PC
- **Esempio dai tuoi appunti:**
    - access-list 10 permit host 10.0.0.1 (Permette al PC 1)
    - access-list 10 permit host 10.0.0.2 (Permette al PC 2)
    - access-list 10 permit host 10.0.0.200 (Permette al Server o PC 3)
    - access-list 10 deny any (Blocca tutti gli altri che non sono in lista)

Consiglio Universale: Se vuoi fare prima e permettere a **tutta** la rete 10.0.0.0, potresti scrivere: access-list 10 permit 10.0.0.0 0.255.255.255.

---
### Passaggio 5: Attivazione del NAT con Overload (PAT)
Questo è il comando finale che "unisce i puntini": collega la lista dei PC (ACL 10) al pool di IP pubblici (INTERNET).
- **Comando:** ip nat inside source list 10 pool INTERNET overload
- **Perché "overload"?** Questa parola è fondamentale. Permette a tutti i PC della lista 10 di usare lo stesso IP del pool contemporaneamente, distinguendoli tramite le porte (PAT).

---
### Riepilogo Logico per l'esame:
1. **Rotta:** Dico al router di uscire verso l'ISP.
2. **Etichette:** Dico al router qual è l'entrata (inside) e quale l'uscita (outside).
3. **Risorsa:** Definisco l'IP pubblico che mi ha dato l'esame (pool).
4. **Selezione:** Scelgo quali PC interni possono navigare (access-list).
5. **Azione:** Attivo il passaggio dei dati aggiungendo overload.

### Come verificare se funziona:

Una volta configurato, prova a fare un **Ping** da un PC interno verso l'IP dell'ISP (es. 50.0.0.2). Se risponde, scrivi sul router:  
show ip nat translations  
Vedrai la tabella che ti mostra l'IP privato che si trasforma nell'IP pubblico. Se vedi la tabella piena, l'esercizio è corretto! 🎯
	
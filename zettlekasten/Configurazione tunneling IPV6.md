Questa tecnica permette di collegare "isole" che usano un [[Indirizzo IPV6]] facendole transitare attraverso una rete che supporta solo un [[Indirizzo IPV4]].

---
# Tunneling IPv6 su IPv4
### [[Processo configurazione network]]

Il concetto è creare un "ponte" virtuale (Interfaccia Tunnel) tra due router. Tutto il traffico IPv6 viene impacchettato dentro pacchetti IPv4 per poter attraversare la rete non aggiornata.

### 1. Requisiti Preliminari
Prima di iniziare, i due router devono potersi "pingare" via IPv4 sulle loro interfacce seriali o WAN.
- Assicurati di aver abilitato il routing IPv6 su entrambi i router con il comando: ipv6 unicast-routing.
---
### 2. Configurazione Router A (Inizio del Tunnel)
In questo router creiamo l'interfaccia virtuale e definiamo dove deve puntare.
1. **Creare l'interfaccia:** interface tunnel 0
2. **Definire l'origine (fisica):** tunnel source se0/0/0
    - Nota: Usa il nome della porta seriale o ethernet che ha l'IP pubblico/WAN.
3. **Definire la destinazione (remota):** tunnel destination 160.0.0.2
    - Nota: Questo è l'indirizzo IPv4 dell'interfaccia WAN dell'altro router.
4. **Assegnare IPV6 al Tunnel:**
    - ipv6 address 3000::1/64 (IP globale del tunnel)
    - ipv6 address fe80::1 link-local (Indirizzo locale necessario per il routing)
5. **Abilitare il Routing Protocol:** ipv6 rip cisco enable
    - Nota: Questo attiva il protocollo RIPng all'interno del tunnel.
6. **Specificare il tipo di tunnel:** tunnel mode ipv6ip
    - Significato: Incapsula IPv6 direttamente in IPv4.
---
### 3. Configurazione Router B (Fine del Tunnel)

Dobbiamo fare la configurazione speculare. La destinazione di B sarà l'origine di A.
1. **Creare l'interfaccia:** interface tunnel 0
2. **Assegnare IPV6 al Tunnel:**
    - ipv6 address 3000::2/64
    - ipv6 address fe80::2 link-local
3. **Abilitare il Routing Protocol:** ipv6 rip cisco enable
4. **Definire l'origine (fisica):** tunnel source se0/0/1
5. **Definire la destinazione (remota):** tunnel destination 150.0.0.1
    - Nota: Questo deve essere l'indirizzo IPv4 WAN del Router A.
6. **Specificare il tipo di tunnel:** tunnel mode ipv6ip
---
### 4. Propagazione della Rete Locale (LAN)
Per far sì che i PC collegati ai router possano parlarsi, dobbiamo dire al protocollo di routing di includere anche le interfacce delle LAN.
- Sul router, entra nell'interfaccia dove è collegata la LAN (es. interface fa0/0).
- Digita: ipv6 rip cisco enable.
- Questo comando dice al router: "Prendi la rete IPv6 di questa LAN e annunciala attraverso il tunnel all'altro router".
---
### Riepilogo Concettuale per l'Esame:
- **Perché usiamo il Tunnel?** Per collegare reti IPv6 separate da una rete IPv4.
- **Cos'è il Tunnel Source?** È l'interfaccia fisica (IPv4) da cui parte il tunnel.
- **Cos'è il Tunnel Destination?** È l'IP pubblico (IPv4) del router dall'altra parte del mondo.
- **Cos'è il Tunnel Mode?** È il "linguaggio" di incapsulamento (ipv6ip).
- **A cosa serve il RIP?** Serve a far imparare ai router quali reti IPv6 ci sono dietro il tunnel senza dover scrivere le rotte a mano.

Parte di: [[Configurazione rete IPV6]]

Se vuoi verificare la configurazione nel simulatore, usa il comando show ipv6 interface brief per vedere se l'interfaccia Tunnel 0 è "up/up". Se è "up/down", ricontrolla gli indirizzi tunnel destination.
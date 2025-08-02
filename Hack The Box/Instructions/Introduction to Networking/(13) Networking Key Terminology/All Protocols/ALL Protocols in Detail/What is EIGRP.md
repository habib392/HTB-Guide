## EIGRP (Enhanced Interior Gateway Routing Protocol)
---

### EIGRP Kya Hai?

EIGRP ek advanced distance-vector protocol hai jo sirf **Cisco devices** par kaam karta hai. Yeh IGRP ka upgraded version hai aur **bandwidth**, **delay**, **load**, aur **reliability** dekh kar best rasta choose karta hai. Classless protocol hai, yani subnet masks bhi routing updates ke sath bhejta hai. Jaldi converge karta hai aur bade networks ke liye perfect hai.

### EIGRP vs IGRP (Differences)

* **Classless**: Subnet masks bhejta hai
* **Faster Convergence**: Routes seconds mein update karta hai
* **Authentication Support**: MD5/SHA
* **Example**: IGRP purani cycle, EIGRP sports bike

### EIGRP vs RIP vs OSPF

* **RIP**: Hops count karta hai (max 15)
* **OSPF**: Bandwidth aur cost dekhta hai
* **EIGRP**: Bandwidth, delay, load, reliability dekhta hai
* **Example**: RIP - cycle, OSPF - Google Maps, EIGRP - smart GPS jo sab kuch dekhta hai

### EIGRP Topology Example

```
R1 ➡️ R10 ➡️ R15 ➡️ R50 ➡️ R78 ➡️ R100
 ↘️     R40 ➡️ R67 ➡️ R89 ➡️ R100
 ↘️     R53 ➡️ R78 ➡️ R100
```

* **3 Rastay**:

  1. 5 hops
  2. 4 hops
  3. 3 hops
* **EIGRP** bandwidth, delay, load check karta hai aur best rasta choose karta hai.

### EIGRP Kaise Kaam Karta Hai?

1. **Composite Metric**: Bandwidth, delay, load, reliability ka combo
2. **DUAL Algorithm**: Fast route finding + backup routes
3. **Triggered Updates**: Sirf changes hone par updates bhejta hai
4. **Autonomous System (AS)**: Sirf same AS number wale routers data share karte hain
5. **Classless**: VLSM support karta hai
6. **Authentication**: MD5/SHA support karta hai (secure)

### EIGRP Use Case

* **Sirf Cisco networks** mein use hota hai (banks, campuses, data centers)
* Example: Bank ke 50 routers wala network - fast & reliable routing

### EIGRP for Penetration Testing

1. **Packet Sniffing** (Wireshark - `eigrp` filter)
2. **Fake Updates** (Scapy se route manipulation)
3. **DoS Attack** (Flooding with fake updates)
4. **Authentication Exploit** (Weak password crack karna)

**Tools**:

* Wireshark
* Scapy
* Ettercap

**Security Tips**:

* Strong auth use karo
* ACLs lagao
* Monitor traffic

### EIGRP Configuration Example

```bash
Router> enable
Router# configure terminal
Router(config)# router eigrp 10
Router(config-router)# network 192.168.1.0 0.0.0.255
Router(config-router)# network 192.168.2.0 0.0.0.255
Router(config-router)# exit
Router(config)# exit
Router# write
```

### Comparison Table

| Feature      | RIP      | OSPF      | IGRP      | EIGRP     |
| ------------ | -------- | --------- | --------- | --------- |
| Type         | DV       | LS        | DV        | Adv-DV    |
| Metric       | Hops     | Cost      | Delay etc | Delay etc |
| Convergence  | Slow     | Fast      | Slow      | Very Fast |
| Network Size | Small    | Large     | Medium    | Large     |
| Class        | Classful | Classless | Classful  | Classless |
| Auth         | Weak     | Strong    | None      | Strong    |
| Devices      | Any      | Any       | Cisco     | Cisco     |

### Next Steps

* GNS3 mein practice kar
* Wireshark mein packets capture kar
* Scapy se fake updates test kar
* BGP seekhna start kar

# IGRP (Interior Gateway Routing Protocol)

## IGRP Kya Hai?
**IGRP (Interior Gateway Routing Protocol)** ek **distance-vector routing protocol** hai jo sirf **Cisco routers** ke liye hai. Yeh data packets ke liye sabse behtar rasta chunta hai, lekin RIP se zyada advanced hai kyunke yeh **delay**, **bandwidth**, aur **load** dekhta hai, na ke sirf hops. IGRP ki hop limit **100** hai, lekin isay **255** tak barhaya ja sakta hai.

**RIP aur OSPF se Farq**:
- **RIP**: Sirf hops dekhta hai (max 15), chhote networks ke liye.
- **OSPF**: Bandwidth aur cost ke hisaab se routes chunta hai, bade networks ke liye.
- **IGRP**: Delay, bandwidth, aur load dekhta hai, aur Cisco-only hai.
- **Example**: RIP cycle jaisa hai jo turns count karta hai. OSPF Google Maps jaisa hai jo road quality dekhta hai. IGRP aisa hai jo traffic, road speed, aur load sab dekhta hai.

## IGRP Ki Topology

```
🔳R1 ➡️ 🔳R10 ➡️ 🔳R15 ➡️ 🔳R50 ➡️ 🔳R78 ➡️ 🔳R100
  ↘️       🔳R40 ➡️ 🔳R67 ➡️ 🔳R89 ➡️ 🔳R100
  ↘️       🔳R53 ➡️ 🔳R78 ➡️ 🔳R100
```

- **Scenario**: R1 ko R100 tak data bhejna hai. Teen raste hain:
  1. R1 → R10 → R15 → R50 → R78 → R100 (5 hops)
  2. R1 → R40 → R67 → R89 → R100 (4 hops)
  3. R1 → R53 → R78 → R100 (3 hops)
- **IGRP Ka Approach**: IGRP hops ke saath **delay**, **bandwidth**, aur **load** dekhta hai. Agar rasta no. 3 ka delay aur load kam hai (chahe hops zyada hon), to IGRP usay chunay ga.
- **Example**: IGRP aisa hai jaise tu road trip ke liye rasta chune, jahan tu na sirf distance, balke traffic jam aur road speed bhi dekhta hai.

## IGRP Kaise Kaam Karta Hai?
1. **Metrics**:
   - IGRP routes chunne ke liye **delay**, **bandwidth**, **load**, aur **reliability** dekhta hai. Yeh RIP se zyada smart hai kyunke hops ke alawa network conditions bhi consider karta hai.
   - **Example**: Agar ek rasta short hai lekin slow hai, to IGRP doosra rasta chunay ga jahan speed zyada ho.
2. **Updates**:
   - IGRP har **90 seconds** mein routing updates bhejta hai doosre routers ko.
   - **Example**: Yeh aisa hai jaise tu har 90 seconds mein apne doston ko WhatsApp par apni location update karta hai.
3. **Hop Limit**:
   - IGRP ki default hop limit **100** hai, lekin isay **255** tak barhaya ja sakta hai. Yeh RIP (15 hops) se bohot zyada hai.
   - **Example**: Ek network mein 100 Cisco routers ho to IGRP kaam kar sakta hai, jabke RIP band ho jata.

## Autonomous System (AS) Kya Hai?
- IGRP ek **Autonomous System (AS)** ke andar kaam karta hai, jiska number **1 se 65535** tak ho sakta hai.
- Jab tu `router igrp 10` set karta hai, to sirf woh routers jo AS 10 use karte hain, apas mein routes share karte hain. Doosre AS (jaise AS 20) ke routers se baat nahi hoti.
- **Example**: AS aisa hai jaise WhatsApp group. Sirf AS 10 ke routers ek group mein hote hain aur info share karte hain. AS 20 wala group alag hota hai.

## Classful Protocol Kya Hai?
- IGRP ek **classful protocol** hai, yani yeh routing updates mein **subnet mask** nahi bhejta. Yeh assume karta hai ke IP address ki class (A, B, C) ke default mask use ho rahe hain.
  - **Example**: Agar tu 192.168.1.0 use karta hai, to IGRP isay Class C (255.255.255.0) samajhta hai, chahe tu ne /26 subnet use kiya ho.
- **Problem**: IGRP **VLSM (Variable Length Subnet Masking)** support nahi karta, isliye modern networks mein iski jagah EIGRP ya OSPF use hota hai.
- **Example**: Agar tu ek network ko chhote subnets mein divide karna chahta hai, to IGRP kaam nahi karega, lekin OSPF ya EIGRP karenge.

## IGRP Kahan Use Hota Hai?
- IGRP sirf **Cisco devices** par kaam karta hai, isliye bade Cisco-based networks (jaise offices, campuses) mein use hota tha.
- **Example**: Ek bank ke offices mein 50 Cisco routers hain. IGRP unke darmiyan routes chunta hai taake data tezi se transfer ho.
- **Note**: IGRP ab outdated hai, aur iski jagah **EIGRP (Enhanced IGRP)** use hota hai jo zyada advanced aur flexible hai.

## IGRP aur Penetration Testing
IGRP ke weaknesses ko pentesting mein exploit kar sakta hoon:
1. **Packet Sniffing**:
   - **Wireshark** se IGRP packets capture kar ke network topology samajh sakta hoon.
   - **Example**: Ek office ke network mein IGRP packets dekh kar pata laga sakta hoon ke kaunse routers critical hain.
2. **Fake Updates**:
   - **Scapy** se fake IGRP updates bhej kar routes redirect kar sakta hoon.
   - **Example**: Fake update se bol sakta hoon ke R100 ka rasta mere laptop se hai, aur traffic mujhe aaye.
3. **DoS Attack**:
   - IGRP updates ko flood kar ke routers overload kar sakta hoon.
   - **Example**: Test lab mein fake updates se network slow kar sakta hoon.
4. **No Authentication**:
   - IGRP mein authentication nahi hota, to fake updates bhejna asaan hai.
   - **Example**: Ek Cisco network mein fake routes inject kar ke data intercept kar sakta hoon.

**Tools**:
- Wireshark: IGRP packets capture ke liye.
- Scapy: Fake updates bhejne ke liye.
- Ettercap: MITM attacks ke liye.

**Security Tips**:
- IGRP ke bajaye EIGRP use karo kyunke usme authentication hota hai.
- ACLs laga do taake sirf trusted routers updates bhej saken.
- Network traffic monitor karo fake updates ke liye.

## IGRP Configuration
Cisco router par IGRP configure karne ke commands:

```plaintext
Router> enable
Router# configure terminal
Router(config)# router igrp 10
Router(config-router)# network 192.168.1.0
Router(config-router)# network 192.168.2.0
Router(config-router)# exit
Router(config)# exit
Router# write
```

**Explanation**: Yeh commands AS 10 ke saath IGRP enable karte hain aur do networks (192.168.1.0 aur 192.168.2.0) ko advertise karte hain.

## Agla Step
- **Practice**: GNS3 mein IGRP configure karo.
- **Packet Analysis**: Wireshark se IGRP packets dekho.
- **Attacks**: Scapy se fake updates test karo.
- **EIGRP Seekho**: IGRP ke baad EIGRP next hai kyunke yeh modern aur better hai.


---


# OSPF (Open Shortest Path First)

## OSPF Kya Hai?
**OSPF (Open Shortest Path First)** ek **link-state routing protocol** hai jo bade networks mein routers ke darmiyan sabse tezi wala rasta chunta hai. Yeh **bandwidth** aur **latency** dekhta hai, na ke sirf hops jaisa ke RIP karta hai. Yeh open standard hai, yani har router (Cisco, Juniper) ke saath kaam karta hai.

**RIP se Farq**:
- RIP hops count karta hai (max 15).
- OSPF cost (bandwidth-based) dekhta hai.
- **Example**: RIP cycle jaisa hai jo turns count karta hai. OSPF Google Maps jaisa hai jo road quality aur traffic dekhta hai.

## OSPF Ki Topology
Maine ek topology banayi thi jo OSPF ka kaam dikhati hai:

```
    🔳R4 (10Mbps) ➡️ 🔳R5 (100Mbps) 
↗️                           ↘️
🔳R1 ➡️ 🔳R2 (1Gbps) ➡️ 🔳R3
  ↘️                           ↗️
  🔳R6 (100Mbps) ➡️ 🔳R7 (10Mbps) ➡️ 🔳R8 (10Mbps)
```

- **Scenario**: R1 ko R3 tak data bhejna hai. Teen raste hain:
  1. R1 → R4 → R5 → R3 (3 hops, cost = 11)
  2. R1 → R2 → R3 (2 hops, cost = 0.2)
  3. R1 → R6 → R7 → R8 → R3 (4 hops, cost = 21)
- OSPF rasta no. 2 chunay ga kyunke iska **cost** (0.2) sabse kam hai aur yeh 1Gbps link hai.
- **Example**: OSPF motorway chunta hai kyunke yeh tezi se pohnchata hai, na ke slow sadak.

## OSPF Kaise Kaam Karta Hai?
1. **Link-State Advertisements (LSAs)**:
   - Har router apne links ki info (speed, status) LSAs ke roop mein bhejta hai.
   - **Example**: Lahore ka router kehta hai, “Main Lahore hoon, mera link 100Mbps ka hai, aur main Karachi se connected hoon.”
2. **Link-State Database (LSDB)**:
   - Sare LSAs LSDB mein store hote hain, jo har router ke paas hota hai. Yeh network ka poora map hai.
   - **Example**: LSDB Google Maps jaisa hai jisme sare routers ke raste hote hain.
3. **Dijkstra’s Algorithm**:
   - OSPF is algorithm se sabse kam cost wala rasta chunta hai.
   - **Example**: Google Maps bhi yeh algorithm use karta hai shortest route ke liye.
4. **Areas**:
   - OSPF bade networks ko areas mein divide karta hai. Ek **Area Border Router (ABR)** areas ko connect karta hai.
   - **Example**: Ek building ke 5 floors (5 areas) ke routers ABR se connect hote hain.

## Office Example (Islamabad, Lahore, Karachi)
Ek office ka head office Islamabad mein hai, aur branches Lahore aur Karachi mein hain:
- **Islamabad Router**: OSPF configure hai, Area 0 (backbone) mein hai, aur ABR hai.
- **Lahore aur Karachi Routers**: Apne LSAs (speed, state) Islamabad ke router ko bhejte hain.
- Har router ke paas LSDB hota hai jo network ka map rakhta hai.
- **Example**: Islamabad ka router aisa hai jaise head office jo Lahore aur Karachi ke updates ek central map mein rakhta hai.

## Building Example (5 Floors)
Ek building mein 5 floors hain, har floor ek area hai:
- **Floor 1 → Area 1, Floor 2 → Area 2, ..., Floor 5 → Area 5**.
- Har floor ka router apne area ke LSAs share karta hai.
- **Router 1 (ABR)** sare floors ko Area 0 ke zariye connect karta hai.
- **Example**: Router 1 building ka main gatekeeper hai jo har floor ke messages doosre floors tak pohanchata hai.

## OSPF Kahan Use Hota Hai?
- **Corporate Networks**: Banks, IT firms ke bade networks.
  - **Example**: Ek bank ke branches OSPF se connect hote hain.
- **Data Centers**: AWS, Google ke servers.
  - **Example**: Google Drive file upload OSPF routes se jati hai.
- **ISPs**: Internal network routing.
  - **Example**: PTCL ka network OSPF use karta hai.
- **University Campuses**: Wi-Fi networks.
  - **Example**: University ka Wi-Fi OSPF se sync hota hai.

## OSPF aur Penetration Testing
OSPF ke weaknesses ko pentesting mein exploit kar sakta hoon:
1. **Packet Sniffing**:
   - **Wireshark** se OSPF packets (`ospf` filter) capture kar ke topology samajh sakta hoon.
   - **Example**: Bank ke network mein OSPF packets se Islamabad router ka role pata kar sakta hoon.
2. **Fake LSAs**:
   - **Scapy** se fake LSAs bhej kar routes redirect kar sakta hoon.
   - **Example**: Fake LSA se Karachi ka traffic apne laptop par bhej sakta hoon.
3. **DoS Attack**:
   - LSAs flood kar ke routers overload kar sakta hoon.
   - **Example**: Test lab mein fake LSAs se network slow kar sakta hoon.
4. **Weak Authentication**:
   - Weak MD5 password crack kar ke network control kar sakta hoon.
   - **Example**: University network mein weak password se routes manipulate kar sakta hoon.

**Tools**:
- Wireshark: OSPF packets ke liye.
- Scapy: Fake LSAs bhejne ke liye.
- Ettercap: MITM attacks ke liye.

**Security Tips**:
- Strong MD5/SHA authentication use karo.
- ACLs laga do taake sirf trusted routers OSPF packets bhej saken.
- Fake LSAs ke liye traffic monitor karo.

## OSPF Configuration
### Office Scenario (Islamabad, Lahore, Karachi)
```plaintext
# Islamabad Router (ABR, Area 0)
Router> enable
Router# configure terminal
Router(config)# router ospf 1
Router(config-router)# network 192.168.1.0 0.0.0.255 area 0
Router(config-router)# network 192.168.2.0 0.0.0.255 area 1  # Lahore
Router(config-router)# network 192.168.3.0 0.0.0.255 area 2  # Karachi
Router(config-router)# exit

# Lahore Router (Area 1)
Router(config)# router ospf 1
Router(config-router)# network 192.168.2.0 0.0.0.255 area 1
Router(config-router)# exit

# Karachi Router (Area 2)
Router(config)# router ospf 1
Router(config-router)# network 192.168.3.0 0.0.0.255 area 2
Router(config-router)# exit
```

### Building Scenario (5 Floors)
```plaintext
# Router 1 (ABR, Area 0)
Router(config)# router ospf 1
Router(config-router)# network 192.168.0.0 0.0.0.255 area 0  # Backbone
Router(config-router)# network 192.168.1.0 0.0.0.255 area 1  # Floor 1
Router(config-router)# network 192.168.2.0 0.0.0.255 area 2  # Floor 2
Router(config-router)# network 192.168.3.0 0.0.0.255 area 3  # Floor 3
Router(config-router)# network 192.168.4.0 0.0.0.255 area 4  # Floor 4
Router(config-router)# network 192.168.5.0 0.0.0.255 area 5  # Floor 5
Router(config-router)# exit

# Floor 1 Router (Area 1)
Router(config)# router ospf 1
Router(config-router)# network 192.168.1.0 0.0.0.255 area 1
Router(config-router)# exit
# Same for Floor 2, 3, 4, 5
```

**Example**: Yeh commands office ya building ke routers ko OSPF se sync karte hain.

## Agla Step
- **Practice**: GNS3 mein OSPF configure karo.
- **Packet Analysis**: Wireshark se OSPF packets dekho.
- **Attacks**: Scapy se fake LSAs test karo.
- **BGP Seekho**: Internet routing ke liye BGP next hai.



---

### Note Explanation
Habib bhai, yeh note bilkul teri zuban mein hai aur maine sirf **main points** rakhe hain:
- Teri di hui topology aur examples (office aur building).
- OSPF ke core concepts (LSAs, LSDB, areas, ABR).
- Penetration testing ke key points aur tools.
- Configurations tere scenarios ke hisaab se.

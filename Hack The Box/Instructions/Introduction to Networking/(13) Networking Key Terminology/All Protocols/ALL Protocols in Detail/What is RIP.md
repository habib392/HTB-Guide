# Routing Information Protocol (RIP)

## RIP Kya Hai?
Main ne seekha ke **Routing Information Protocol (RIP)** ek **dynamic routing protocol** hai jo chhote networks mein routers ke darmiyan data packets ke raste (routes) decide karta hai. Yeh ek **open standard protocol** hai, yani yeh har company ke routers (Cisco, Juniper, etc.) ke saath kaam kar sakta hai. RIP ka kaam hai ke data packets ko sabse kam **hops** (routers ke darmiyan jumps) wale raste se bheje taake data jaldi apni manzil tak pohnche.

### Dynamic vs Static Routing
Mujhe pehle nahi pata tha ke dynamic aur static routing mein kya farq hai, lekin ab clear hai:
- **Static Routing**: Isme network admin manually routes set karta hai. Yeh chhote aur fixed networks ke liye theek hai, lekin agar network change ho to bohot mehnat lagti hai.
- **Dynamic Routing**: RIP jaisa protocol khud hi routes discover aur update karta hai. Har 30 seconds mein RIP updates bhejta hai, jo network ke changes ke hisaab se routes adjust karta hai.
- **Example**: Static routing aisa hai jaise GT Road ka fixed rasta chunna. Dynamic routing aisa hai jaise GPS use karna jo traffic ke hisaab se naya rasta batata hai.

## RIP Kaise Kaam Karta Hai?
RIP **distance-vector protocol** hai, yani yeh hop count ke hisaab se routes chunta hai. Yeh har router ke paas ek **Routing Information Table** hoti hai jisme doosre routers aur networks ki info hoti hai. Har 30 seconds baad RIP apni table ke updates doosre routers ko bhejta hai taake sab ke paas latest routes hon.

### Example
Maine ek diagram banaya tha jo RIP ke kaam ko samjhaata hai:

```
    🔳R4 ➡️ 🔳R5 
↗️                        ↘️
🔳R1 ➡️ 🔳R2 ➡️ 🔳R3
  ↘️                        ↗️
  🔳R6 ➡️ 🔳R7 ➡️ 🔳R8
```

- Agar **R1** ko **R3** tak data bhejna hai, to teen raste hain:
  1. R1 → R4 → R5 → R3 (3 hops)
  2. R1 → R2 → R3 (2 hops)
  3. R1 → R6 → R7 → R8 → R3 (4 hops)
- RIP sabse kam hops wala rasta chunay ga, yani rasta no. 2 (2 hops). Yeh RIP ka basic kaam hai ke woh kam hops wale raste se data bhejta hai, chahe woh rasta slow hi kyun na ho.

### RIP Ki Limit
RIP sirf **15 hops** tak kaam karta hai. Agar koi network 16 hops door hai, to RIP usay “unreachable” mark karta hai. Is wajah se RIP chhote networks (jaise office ya college) ke liye hai, bade networks ya internet ke liye nahi.

## Real-Life Example
Jab main apne phone se **Facebook.com** open karta hoon, to meri request pehle mere Wi-Fi router tak jati hai. Router dekhta hai ke uska nazdeeki router kaunsa hai, aur request wahan bhejta hai. Agar local network mein RIP use ho raha ho, to yeh request kam hops wale raste se aage badhti hai. Lekin internet ke scale par RIP ka use nahi hota kyunke uski 15 hops ki limit hai. Internet ke liye **BGP (Border Gateway Protocol)** use hota hai jo global routes manage karta hai.

- **Example**: RIP aisa hai jaise local bus service jo chhote stops ke liye hai. BGP international flights ke jaisa hai jo duniya bhar ke routes handle karta hai.

## Routing Information Table aur Updates
RIP ke har router ke paas ek **Routing Information Table** hoti hai jisme yeh info hoti hai ke kaunsa router kis network tak jata hai aur kitne hops lagte hain. Jaise:
- Agar **Facebook.com** ke server tak pohnchna hai, to router table se dekhta hai ke nazdeeki router kaunsa hai.
- Agar **Pakwheels.com** ke server tak request jati hai, to router table ke hisaab se doosre router ko request bhejta hai.

RIP har 30 seconds baad updates bhejta hai. Agar koi naya router add ho ya koi rasta band ho jaye, to RIP table ko update karta hai. Jaise agar pehle **Facebook.com** tak 10 hops lagte thay, lekin ab naya shortcut mil gaya jo 8 hops ka hai, to RIP yeh info sab routers ke saath share karta hai.

### Extra Detail
- RIP updates **UDP port 520** par bheje jate hain.
- **RIPv2** multicast address (224.0.0.9) use karta hai, jo network traffic ko kam karta hai.
- RIP ke updates mein **split horizon** aur **poison reverse** jaise rules hote hain taake routing loops na hon.

## RIP Ke Versions
- **RIPv1**: Purana version hai, classful routing karta hai (subnet masks ko ignore karta hai). Yeh ab kam use hota hai kyunke modern networks ke liye kaafi limited hai.
- **RIPv2**: Upgraded version hai, classless routing aur authentication support karta hai. Yeh chhote networks ke liye ab bhi useful hai.

## RIP Ki Limitations
- **15 Hops Ki Limit**: Bade networks ke liye kaam nahi karta.
- **Slow Convergence**: Agar koi router fail ho jaye, to naye raste dhoondne mein 1-2 minute lag sakte hain.
- **Bandwidth Waste**: Har 30 seconds ke updates se network traffic badh sakta hai.
- **Security Weakness**: RIPv1 mein authentication nahi hota, aur RIPv2 ka authentication bhi modern standards ke muqable weak hai.

## RIP aur Penetration Testing
Penetration testing ke liye RIP ko samajhna zaroori hai kyunke iske weaknesses ko exploit kiya ja sakta hai:

1. **Network Enumeration**:
   - RIP updates ko **Wireshark** se capture kar ke network ka layout (topology) samajh sakta hoon. Filter laga ke (`udp.port == 520`) RIP packets dekh sakta hoon.
   - **Example**: Ek company ke network mein RIP updates dekh kar main samajh sakta hoon ke kitne routers hain aur kaunse critical hain.

2. **Man-in-the-Middle (MITM) Attack**:
   - RIPv1 mein authentication nahi hota, to **Scapy** ya **Ettercap** se fake RIP updates bhej kar data ko galat raste par redirect kar sakta hoon.
   - **Example**: Main fake RIP update bhej kar routers ko bol sakta hoon ke **Facebook.com** ka server meri machine hai, aur saara traffic mere paas aayega.

3. **Denial of Service (DoS)**:
   - RIP updates ko flood kar ke routers ko overload kar sakta hoon, jisse network down ho jaye.
   - **Example**: Ek test network mein bohot saare fake updates bhej kar main network ko crash kar sakta hoon.

4. **Weak Authentication Exploit**:
   - Agar RIPv2 ka password weak hai (jaise “admin123”), to usay crack kar ke network mein ghus sakta hoon.
   - **Example**: Ek university network mein RIPv2 ka weak password crack kar ke main routes control kar sakta hoon.

### Pentesting Tools
- **Wireshark**: RIP packets capture aur analyze karne ke liye.
- **Scapy**: Fake RIP updates bhejne ke liye.
- **Ettercap**: MITM attacks ke liye.

## RIP Security Best Practices
- **RIPv2 Use Karo**: RIPv1 se bacho kyunke yeh insecure hai.
- **MD5 Authentication**: RIPv2 mein strong passwords ke saath MD5 authentication set karo.
- **Access Control Lists (ACLs)**: Routers par ACLs laga do taake sirf trusted devices RIP updates bhej saken.
- **Monitoring**: Network traffic monitor karo taake fake updates ka pata chal sake.

## RIP vs Doosre Protocols
- **OSPF (Open Shortest Path First)**: Yeh link-state protocol hai jo RIP se zyada advanced hai. Yeh bandwidth aur latency bhi dekhta hai, isliye bade networks ke liye behtar hai.
  - **Example**: Ek data center OSPF use karega, jabke chhota office RIP.
- **BGP (Border Gateway Protocol)**: Internet ke backbone ke liye hai. Yeh policies ke hisaab se routes chunta hai.
  - **Example**: ISPs BGP use karte hain, jabke local network RIP ya OSPF.
- **EIGRP (Enhanced Interior Gateway Routing Protocol)**: Cisco ka proprietary protocol hai jo RIP se zyada efficient hai.

## RIP Configuration Example
Cisco router par RIP configure karne ka basic command set:

```plaintext
Router> enable
Router# configure terminal
Router(config)# router rip
Router(config-router)# version 2
Router(config-router)# network 192.168.1.0
Router(config-router)# network 192.168.2.0
Router(config-router)# exit
Router(config)# exit
Router# write
```

Yeh command do networks (192.168.1.0 aur 192.168.2.0) ko RIP ke through advertise karta hai.

## Agla Step Kya Hai?
- **Practical Practice**: GNS3 ya Packet Tracer mein RIP configure kar ke test karo.
- **Packet Analysis**: Wireshark se RIP packets capture aur analyze karo.
- **Attacks Simulate**: Scapy se fake RIP updates bhej ke MITM attacks practice karo.
- **OSPF Seekho**: RIP ke baad OSPF samajhna zaroori hai kyunke yeh modern networks mein zyada common hai.


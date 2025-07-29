# IGRP, EIGRP, aur PGP Protocols

## **IGRP (Interior Gateway Routing Protocol)**

### **Kya Hai?**
- IGRP ek purana Cisco ka protocol hai jo routers ko batata hai ke data packets ko network mein kaunsa path le kar jana hai. Yeh ek “basic GPS” jaisa tha jo RIP se zyada acha tha, lekin ab outdated hai kyunki EIGRP ne iski jagah le li.

### **Main Purpose**
- Routers ke beech info share karna taake data packets sahi aur acha path le kar destination tak jayein.
- Medium-sized networks mein reliable routing dena.

### **Kahan Use Hota Hai?**
- Purane Cisco networks mein (1980s-1990s), jaise old offices ya companies.
- Aaj kal shayad hi use hota hai kyunki EIGRP aur OSPF zyada behtar hain.
- Kabhi kabhi legacy systems mein jahan purane Cisco routers abhi bhi hain.

### **All Uses**
- **Routing**: Routers ko batana ke data kahan bhejna hai (jaise local server ya internet).
- **Path Selection**: Best path chunna based on bandwidth, delay, aur reliability.
- **Network Stability**: Medium-sized networks mein routing tables ko stable rakhta tha.

### **Kaun Use Karta Hai?**
- **IT Log**: Network admins jo purane Cisco routers chalate the, IGRP set karte the.
- **Aam Log**: Indirectly use karte the jab purane networks pe kaam karte the, lekin unko IGRP ka pata nahi hota tha.

### **Internet ke Saath ya Bina?**
- **Internet ke Saath**: IGRP internet-based networks mein routes manage karta tha (jaise office ka internet traffic).
- **Bina Internet**: Local networks mein bhi kaam karta tha (jaise office ke servers tak data bhejne ke liye).

### **Milty Julte Protocols**
- **RIP**: Simple routing protocol, lekin IGRP se kam acha kyunki sirf hop count dekhta hai.
- **EIGRP**: IGRP ka advanced version, zyada tez aur scalable.
- **OSPF**: Non-Cisco protocol, IGRP se modern aur bade networks ke liye.
- **Farq**: IGRP Cisco ke liye tha aur RIP se behtar, lekin EIGRP aur OSPF se purana aur slow.

### **Cyber Security Mein Kyun Zaroori?**
- **Risks**: 
  - IGRP mein authentication nahi thi, isliye hackers fake routes daal sakte the.
  - Misconfigured IGRP se traffic redirect ho sakta tha.
- **Kya Seekhna Zaroori**: 
  - IGRP ke limitations samajhna (bas basic info kaafi hai kyunki outdated hai).
  - Modern protocols (EIGRP, OSPF) ke secure features seekhna.
  - **Wireshark** se routing packets check karna.
  - Route poisoning attacks samajhna.

### **Real-Life Examples**
- **Old Office Network**: 1990s mein ek office ke Cisco routers IGRP use karte the taake computers se file server ya internet tak data jaye.
- **Legacy System**: Ek purana bank network IGRP use karta tha kyunki unke routers upgrade nahi hue.
- **Small Company**: Chhoti company ke network mein IGRP data ka path decide karta tha.

### **Kya Aaj Kal Chalta Hai?**
- Nahi, IGRP ab outdated hai. EIGRP aur OSPF ne iski jagah le li kyunki woh zyada tez aur secure hain.

## **EIGRP (Enhanced Interior Gateway Routing Protocol)**

### **Kya Hai?**
- EIGRP Cisco ka ek advanced routing protocol hai, jo IGRP ka upgraded version hai. Yeh routers ko batata hai ke data packets ko sabse tez aur reliable path se kahan bhejna hai. Yeh ek “smart GPS” jaisa hai jo Cisco networks ke liye bohat powerful hai.

### **Main Purpose**
- Routers ke beech tez aur advanced routing info share karna taake data packets fastest path se jayein.
- Bade Cisco networks mein tez, scalable, aur reliable routing dena.

### **Kahan Use Hota Hai?**
- Bade Cisco-based networks mein, jaise companies, universities, aur data centers.
- Modern Cisco setups jahan high speed aur reliability chahiye.
- Cloud environments ke Cisco networks mein.

### **All Uses**
- **Routing**: Routers ko best path batana based on bandwidth, delay, reliability, aur load.
- **Scalability**: Bade networks mein hazaron routes manage karna.
- **Fault Tolerance**: Agar ek path fail ho, EIGRP jaldi doosra path dhoondhta hai.
- **Authentication**: EIGRP mein MD5 ya SHA authentication hoti hai jo routes ko secure rakhti hai.

### **Kaun Use Karta Hai?**
- **IT Log**: Network admins jo Cisco networks chalate hain, EIGRP set karte hain.
- **Aam Log**: Indirectly use karte hain jab Cisco-based office ya university network pe kaam karte hain (jaise Wi-Fi ya file sharing), lekin unko EIGRP ka pata nahi hota.

### **Internet ke Saath ya Bina?**
- **Internet ke Saath**: EIGRP internet-based networks mein routes manage karta hai (jaise office ka internet traffic).
- **Bina Internet**: Local networks mein bhi kaam karta hai (jaise data center ke internal traffic ke liye).

### **Milty Julte Protocols**
- **IGRP**: EIGRP ka purana version, lekin kam tez aur efficient.
- **OSPF**: Non-Cisco protocol, EIGRP jaisa powerful lekin open standard.
- **RIP**: Simple protocol, EIGRP se bohat slow aur limited.
- **Farq**: EIGRP Cisco ke liye optimized hai, OSPF open standard hai, IGRP purana hai, aur RIP chhote networks ke liye.

### **Cyber Security Mein Kyun Zaroori?**
- **Risks**: 
  - Agar EIGRP thik se set nahi hai (jaise weak authentication), hackers fake routes daal sakte hain ya traffic redirect kar sakte hain.
  - EIGRP packets intercept ho sakte hain agar secure nahi hain.
- **Kya Seekhna Zaroori**: 
  - EIGRP ke authentication (MD5 ya SHA) set karna.
  - **Wireshark** se EIGRP packets check karna.
  - Route manipulation attacks aur prevention seekhna.

### **Real-Life Examples**
- **Corporate Network**: Ek badi company ke Cisco routers EIGRP use karte hain taake head office se branch office tak data tez jaye.
- **University Network**: University ke Cisco network mein EIGRP routers ko batata hai ke campus ke alag buildings ke beech data kaunsa path le.
- **Data Center**: Data center ke Cisco routers EIGRP se servers ke beech traffic ko fastest path pe bhejte hain.

### **Kya Aaj Kal Chalta Hai?**
- Haan, EIGRP aaj bhi Cisco networks mein bohat use hota hai kyunki yeh tez, reliable, aur scalable hai.

## **PGP (Pretty Good Privacy)**

### **Kya Hai?**
- PGP ek encryption protocol hai jo data (jaise emails, files) ko secure karta hai taake sirf woh log padh sakein jinke paas key hai. Yeh ek “digital lock” jaisa hai jo private-public key pairs use karta hai.

### **Main Purpose**
- Sensitive data (jaise emails, documents) ko encrypt karna taake hackers na padh sakein.
- Data ki authenticity aur integrity check karna (yani sender genuine hai aur data change nahi hua).

### **Kahan Use Hota Hai?**
- Emails aur messaging mein (jaise secure email services).
- File encryption mein (jaise sensitive documents ko protect karna).
- Privacy-focused communities (jaise journalists, activists) mein.

### **All Uses**
- **Email Encryption**: Emails ko encrypt karna taake sirf receiver padh sake.
- **File Encryption**: Sensitive files (jaise contracts, passwords) ko secure karna.
- **Digital Signatures**: Documents ya emails pe sign karke prove karna ke yeh genuine hain.
- **Data Privacy**: Online ya offline data ko hackers se bachana.

### **Kaun Use Karta Hai?**
- **IT Log**: Security professionals jo sensitive data protect karte hain, PGP set aur use karte hain.
- **Aam Log**: Privacy-conscious log (jaise journalists, activists) PGP use karte hain secure emails ya files ke liye. Aam log kam use karte hain kyunki setup thoda mushkil hai.

### **Internet ke Saath ya Bina?**
- **Internet ke Saath**: PGP emails ya online file sharing ke liye use hota hai.
- **Bina Internet**: Local files ya USB drives pe data encrypt karne ke liye bhi kaam karta hai.

### **Milty Julte Protocols**
- **S/MIME**: Email encryption ke liye similar, lekin zyada corporate use.
- **GPG (GNU Privacy Guard)**: PGP ka open-source version, same kaam karta hai.
- **TLS/SSL**: Web encryption ke liye (jaise HTTPS), lekin PGP emails/files ke liye specific hai.
- **Farq**: PGP emails aur files ke liye hai, S/MIME corporate emails ke liye, GPG open-source hai, aur TLS web browsing ke liye.

### **Cyber Security Mein Kyun Zaroori?**
- **Risks**: 
  - Weak keys ya key mismanagement se PGP encryption break ho sakta hai.
  - Phishing attacks se users fake keys use kar sakte hain.
- **Kya Seekhna Zaroori**: 
  - PGP key generation aur management (public/private keys) seekhna.
  - Tools jaise **GPG** ya **Thunderbird** se PGP emails set karna.
  - Phishing aur key compromise attacks samajhna.

### **Real-Life Examples**
- **Secure Email**: Ek journalist apne source ke saath sensitive info share karne ke liye PGP se email encrypt karta hai.
- **File Sharing**: Tu ek USB pe confidential document encrypt karke friend ko deta hai using PGP, taake sirf woh padh sake.
- **Digital Signature**: Ek software developer apne code ko PGP se sign karta hai taake users verify kar sakein ke yeh genuine hai.

### **Kya Aaj Kal Chalta Hai?**
- Haan, PGP aaj bhi privacy aur security ke liye use hota hai, khusus kar open-source communities aur secure communications mein.

## **Quick Comparison**
- **IGRP**: Purana Cisco routing protocol, medium-sized networks ke liye, lekin ab outdated.
- **EIGRP**: IGRP ka advanced version, Cisco ke liye, bade networks ke liye tez aur reliable.
- **PGP**: Encryption protocol, emails aur files ko secure karta hai, privacy ke liye.

## **Cyber Security Relevance**
- **IGRP**: No authentication, isliye fake routes ka risk. Bas basic info seekhna kaafi hai kyunki outdated hai.
- **EIGRP**: Weak authentication se route manipulation ka risk, isliye secure configurations (MD5/SHA) seekhna zaroori.
- **PGP**: Weak keys ya phishing se compromise ho sakta hai, isliye key management aur secure use seekhna zaroori.

## **Learning Plan**
- **IGRP**: Ispe zyada focus na karo kyunki outdated hai. YouTube pe “IGRP vs EIGRP” tutorials dekho taake comparison clear ho.
- **EIGRP**: Cisco Packet Tracer mein EIGRP configure karo aur bade Cisco network ke routes dekho. TryHackMe pe “Advanced Routing” lab try karo.
- **PGP**: **GPG** install karo (Ubuntu pe `sudo apt install gnupg`) aur ek email ya file encrypt karo. TryHackMe pe “Cryptography Basics” lab try karo.

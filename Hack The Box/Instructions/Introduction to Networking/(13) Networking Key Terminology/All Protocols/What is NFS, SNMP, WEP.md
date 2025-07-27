# NFS, SNMP, aur WEP Protocols

## **NFS (Network File System)**

### **Kya Hai?**
- NFS ek protocol hai jo network mein files aur folders ko share karta hai, jaisa ke woh files apne computer ya phone ke local storage mein hon.
- Yeh ek “magic USB drive” jaisa hai jo network ke zariye sab devices ke liye available hota hai, aur users usko kahin se bhi access kar sakte hain.

### **Main Purpose**
- Network ke zariye files aur folders share karna taake multiple users ya apps unko local storage ki tarah use kar sakein.
- Ek hi file pe kaam karne ke liye, bina data conflict ke.

### **Kahan Use Hota Hai?**
- Linux aur Unix systems mein, jaise universities, offices, aur research labs.
- Cloud aur virtual environments (jaise AWS, VMware) mein file sharing ke liye.
- High-performance computing (HPC) jahan bade datasets share hote hain.

### **Kaun Use Karta Hai?**
- **IT Experts/SysAdmins**: Linux/Unix servers manage karne wale system administrators NFS ko configure aur use karte hain.
- **Aam Log**: Indirectly use karte hain jab companies ya universities NFS-based shared folders provide karti hain. Aam logon ko pata nahi hota ke NFS hai, woh bas shared folders use karte hain.

### **Real-Life Examples**
- **University Lab**: Ek university ke computer lab mein central Linux server pe research data rakha hai. Students apne Linux PCs se NFS ke zariye us data ko access karte hain, jaise ke woh local drive ho. Ek student file edit karta hai, aur doosra student usi file pe kaam kar sakta hai.
- **Cloud Storage**: AWS pe ek company NFS-based storage use karti hai taake developers code aur files share kar sakein. Jab developer code push karta hai, woh NFS ke zariye server pe jata hai.
- **Movie Studio**: Animation studio mein NFS server pe 3D models aur videos rakhe hote hain. Sab artists apne workstations se NFS ke zariye unko access karte hain.

### **Cyber Security Relevance**
- **Risks**: Agar NFS thik se configure nahi hai, hackers unauthorized access le sakte hain ya files chura sakte hain.
- **Kya Seekhna Zaroori**: 
  - NFS permissions (read/write access) aur firewall rules check karna.
  - Tools jaise **Nmap** se NFS shares enumerate karna.

### **Kya Aaj Kal Chalta Hai?**
- Haan, NFS (especially NFSv4) aaj bhi Linux/Unix environments mein fast aur reliable file sharing ke liye use hota hai. Windows ke liye SMB zyada common hai, lekin NFS cross-platform ke liye acha hai.

### **Comparison with SMB**
- NFS aur SMB dono network mein files share karte hain.
- **Farq**: 
  - NFS zyadatar Linux/Unix systems mein use hota hai, aur IT experts isko set karte hain.
  - SMB Windows systems mein common hai, aur aam log bhi asani se use kar sakte hain (jaise folder ya printer sharing).

---

## **SNMP (Simple Network Management Protocol)**

### **Kya Hai?**
- SNMP ek protocol hai jo network devices (jaise routers, switches, printers, servers) ko monitor aur manage karta hai.
- Yeh ek “doctor” ya “security analyst” jaisa hai jo devices ke performance, status, aur health check karta hai aur problems (jaise device down ya suspicious activity) pe alerts bhejta hai.

### **Main Purpose**
- Network devices ke performance (jaise CPU usage, bandwidth) aur status remotely monitor karna.
- Devices ke configurations change karna (jaise bandwidth limits set karna).
- Faults (jaise device crash) ya security issues ke alerts dena.

### **Kahan Use Hota Hai?**
- Offices, data centers, aur ISPs ke networks mein.
- IoT devices (jaise smart cameras, sensors) ke monitoring mein.
- Network management tools (jaise Nagios, Zabbix, SolarWinds) mein.

### **Kaun Use Karta Hai?**
- **IT Experts/Network Admins**: Bade networks manage karne wale admins SNMP ko configure aur use karte hain taake network stable rahe.
- **Aam Log**: Indirectly fayda uthate hain jab companies networks smooth rakhti hain, lekin unko SNMP ka naam nahi pata hota.

### **Real-Life Examples**
- **Office Network**: Company ke IT admin SNMP se router aur printer ka status check karta hai. Agar printer ka toner khatam ho, SNMP alert bhejta hai taake admin usko replace kare.
- **Data Center**: Cloud provider (jaise Google Cloud) SNMP se servers ke CPU, memory, aur bandwidth monitor karta hai. Agar server overload ho, SNMP trap bhejta hai, aur team issue fix karti hai.
- **Smart City**: Islamabad ke traffic cameras SNMP se monitored hote hain. Agar koi camera offline ho, SNMP alert bhejta hai taake authorities check kar sakein.
- **Home Network**: Ghar ke Wi-Fi router pe SNMP enable hai. IT admin (ya tu) Nagios se router ka bandwidth usage dekhta hai (jaise Android TV Netflix chala raha hai to 60% bandwidth use ho raha hai). Agar router overload ho (jaise 90% CPU load), SNMP email alert bhejta hai.

### **Cyber Security Relevance**
- **Risks**: 
  - SNMPv1 aur v2c insecure hain kyunki data plaintext mein jata hai, aur default “public” community strings hackers exploit kar sakte hain.
  - Weak configurations se hackers device info chura sakte hain.
- **Kya Seekhna Zaroori**: 
  - SNMPv3 ke secure configurations (authentication, encryption) set karna.
  - Tools jaise **Nmap** ya **snmpwalk** se SNMP enumeration karna taake vulnerabilities check ho sakein.

### **Kya Aaj Kal Chalta Hai?**
- Haan, SNMP (especially SNMPv3) aaj bhi network management ka core hai kyunki yeh simple aur scalable hai. SNMPv1/v2c ab insecure hain, isliye avoid kiye jate hain.

### **Practical Example: Router Monitoring with Nagios**
- **Scenario**: Ghar mein Wi-Fi router (IP: 192.168.0.1) hai, jismein mobile, Android TV, aur doosre devices connected hain, ek network banata hai.
- **Steps**:
  1. Router ke admin panel (192.168.0.1) mein SNMP enable karo, community string “public” ya SNMPv3 (username: “monitor”, password: “strongpass123”) set karo.
  2. Ubuntu laptop pe Nagios Core install karo (`sudo apt install nagios4`).
  3. Nagios config file mein router add karo:
     ```bash
     define host {
         use            linux-box
         host_name      MyRouter
         address        192.168.0.1
         check_command  check_snmp
     }
     define service {
         use                 generic-service
         host_name           MyRouter
         service_description SNMP Check
         check_command       check_snmp!-C public -o sysUpTime
     }
     ```
  4. Nagios dashboard (`http://localhost/nagios4`) pe router ka status dekho: uptime (jaise 3 din), bandwidth usage (jaise 60% kyunki Netflix chal raha hai), connected devices (4 devices).
  5. Alerts set karo: Agar router ka CPU load 80% se zyada ho, Nagios email alert bhejega.
- **Outcome**: Tu dashboard pe dekhta hai ke router 3 din se on hai, aur jab Android TV aur gaming chalte hain, load 90% ho jata hai, Nagios alert bhejta hai.

### **Phones, Laptops, Computers as Network Devices?**
- Haan, phones, laptops, aur computers bhi network devices hote hain jab network pe connected hain (Wi-Fi ya LAN). SNMP inko monitor kar sakta hai, lekin zyadatar routers, switches, printers, aur servers pe focus karta hai kyunki yeh network ke core devices hain.
- Example: Tera laptop office network pe hai, SNMP uska bandwidth usage check kar sakta hai, lekin routers/servers zyada common targets hain.

---

## **WEP (Wired Equivalent Privacy)**

### **Kya Hai?**
- WEP ek purana security protocol hai jo wireless networks (Wi-Fi) ko secure karne ke liye use hota tha.
- Yeh data ko encrypt karta tha, lekin ab kam secure hai kyunki hackers aasani se isko break kar sakte hain.

### **Main Purpose**
- Wi-Fi networks ko unauthorized access aur data theft se bachana.
- Data encryption ke zariye network secure karna.

### **Kaun Use Karta Hai?**
- **IT Experts**: Pehle WEP ko Wi-Fi routers set karte waqt use karte the, lekin ab WPA/WPA2/WPA3 ne jagah le li kyunki WEP hackable hai.
- **Aam Log**: Ab shayad hi koi use kare, kyunki modern routers WPA2/WPA3 default dete hain. Pehle aam log bhi indirectly WEP use karte the jab purane routers set karte the.

### **Kahan Use Hota Hai?**
- Pehle ghar, offices, aur public Wi-Fi (jaise coffee shops) mein use hota tha.
- Ab sirf purane devices ya legacy systems mein milta hai.

### **Real-Life Examples**
- **Old Wi-Fi Router**: Pehle coffee shops ke free Wi-Fi mein WEP use hota tha, lekin hackers uske weak encryption ko break kar sakte the.
- **Legacy System**: Ek purana office router jo 2000s ka hai, WEP use karta hai, lekin ab usko replace kiya jata hai.
- **Home Wi-Fi (Pehle)**: 10 saal pehle tu apne ghar ke Wi-Fi pe WEP set karta tha, lekin ab WPA2/WPA3 use hota hai.

### **Cyber Security Relevance**
- **Risks**: WEP ki weak encryption aasani se hack ho sakti hai (tools jaise Aircrack-ng se).
- **Kya Seekhna Zaroori**: 
  - WEP ke weaknesses samajhna aur WPA3 ke secure features seekhna.
  - Tools jaise **Aircrack-ng** se Wi-Fi vulnerabilities test karna.

### **Kya Aaj Kal Chalta Hai?**
- Nahi, WEP ab outdated aur insecure hai. WPA2 aur WPA3 ab standard hain kyunki yeh zyada secure hain.

### **Comparison with WPA**
- WEP aur WPA dono Wi-Fi ko secure karte hain.
- **Farq**: 
  - WEP purana aur hackable hai kyunki weak encryption (RC4) use karta hai.
  - WPA (especially WPA3) modern hai, strong encryption (AES) deta hai, aur hack karna mushkil hai.

---

## **Quick Comparison**
- **NFS**: Files ko network pe share karta hai, Linux/Unix mein common, IT experts ke liye zaroori.
- **SNMP**: Network devices ko monitor aur manage karta hai, IT admins ke liye must, aam log indirectly fayda uthate hain.
- **WEP**: Purana Wi-Fi security protocol, ab outdated, aam log bhi pehle indirectly use karte the.

## **Cyber Security Relevance**
- **NFS**: Weak permissions se hackers files chura sakte hain. NFS shares ke firewall rules aur access controls check karna zaroori.
- **SNMP**: Insecure SNMPv1/v2c aur default community strings hackers exploit karte hain. SNMPv3 ke secure configurations seekhna must hai.
- **WEP**: Weak encryption se hackers Wi-Fi hack kar sakte hain. WPA3 ke features aur Wi-Fi testing tools seekhna zaroori.

## **Learning Plan**
- **NFS**: Linux VM (Ubuntu) pe NFS server set karo aur doosre device se files access karo. TryHackMe pe NFS labs try karo.
- **SNMP**: Nagios ya Zabbix install karo aur apne router ka status monitor karo. Nmap se SNMP scan karo (`nmap -sU -p 161 <IP>`).
- **WEP**: WPA3 ke features samajho aur Aircrack-ng se Wi-Fi testing ke basic tutorials dekho.


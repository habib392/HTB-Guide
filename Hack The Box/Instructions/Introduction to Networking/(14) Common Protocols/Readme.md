**Internet Protocols Kya Hain?**  
Internet protocols ek tarah ke rules ya guidelines hain jo yeh batate hain ke network mein devices ek doosre se kaise baat karenge. Yeh rules RFCs (Request for Comments) mein likhe hote hain. Inka kaam yeh hai ke chahe koi bhi device ho, chahe uska hardware ya software kuch bhi ho, woh ek doosre se sahi tarah se information share kar sakein. Devices ke beech connection chahiye, jaise wired (taar wala) ya wireless (bina taar). Phir yeh devices ek standard protocol ke zariye data bhejte aur lete hain, jo data ka format aur structure batata hai. Do sabse common connections hain: **TCP** aur **UDP**.

**TCP (Transmission Control Protocol) Kya Hai?**  
TCP ek aisa protocol hai jo pehle do devices ke beech ek solid connection banata hai, jise kehte hain **Three-Way-Handshake**. Yeh connection tab tak rehta hai jab tak data transfer poora na ho jaye. Matlab, jab tak connection hai, devices ek doosre ko data bhej sakte hain.

**Example:** Jab tu apne browser mein koi URL daalta hai, jaise “www.google.com”, toh browser ek **HTTP request** website ke server ko bhejta hai, aur yeh kaam TCP ke through hota hai. Server phir website ka **HTML code** browser ko TCP ke zariye bhejta hai. Browser is code ko use karke website ko teri screen pe dikhata hai. Yeh sab tab tak hota hai jab tak TCP connection active hai. TCP reliable hai, lekin thoda slow hai kyunki isme connection banane aur maintain karne mein extra time lagta hai, unlike UDP.

**Kyun Janna Zaroori Hai?**  
Yeh protocols har us communication ka base hain jo humare devices aur computers network mein karte hain. Inko samajhna isliye zaroori hai kyunki jitna achha hum inhe jaanenge, utna hi behtar hum network ke saath kaam kar sakenge. Jaise, agar tu kisi website ya app ke saath kaam kar raha hai, toh TCP ka role samajhna tujhe issues solve karne mein bohot help karega.

---

1. **FTP (File Transfer Protocol)**  
   - **Kaam**: Files transfer karne ke liye.  
   - **Example**: Jaise tu kisi server se badi file download karta hai ya upload karta hai, FTP use hota hai.

2. **NTP (Network Time Protocol) - Port 123**  
   - **Kaam**: Computers ke clocks ko sync karta hai taake sab same time pe chalte rahen.  
   - **Example**: Agar tu Google Calendar use karta hai, toh NTP ensure karta hai ke sab devices pe time ek jaisa ho.

3. **SMTP (Simple Mail Transfer Protocol) - Port 25**  
   - **Kaam**: Email bhejne ke liye.  
   - **Example**: Jab tu Gmail se email bhejta hai, SMTP us email ko server tak pohanchata hai.

4. **POP3 (Post Office Protocol) - Port 110**  
   - **Kaam**: Emails ko server se download karne ke liye.  
   - **Example**: Jab tu Outlook mein emails check karta hai, POP3 unhe server se tere device pe lata hai.

5. **IMAP (Internet Message Access Protocol) - Port 143**  
   - **Kaam**: Emails ko server pe access karne ke liye, bina download kiye.  
   - **Example**: Gmail app mein jab tu emails dekhta hai aur woh server pe hi rehte hain, IMAP kaam karta hai.

6. **SMB (Server Message Block) - Port 445**  
   - **Kaam**: Files transfer karne ke liye, mostly Windows systems mein.  
   - **Example**: Office mein ek shared folder se files lena ya dena, SMB ke through hota hai.

7. **NFS (Network File System) - Port 111, 2049**  
   - **Kaam**: Remote systems ke folders ko access karne ke liye.  
   - **Example**: Jaise tu ek server ke files ko apne computer pe mount karta hai, NFS use hota hai.

8. **BOOTP (Bootstrap Protocol) - Port 67, 68**  
   - **Kaam**: Computers ko network pe start karne mein help karta hai.  
   - **Example**: Jab ek new device network se IP address mangta hai, BOOTP help karta hai.

9. **Kerberos - Port 88**  
   - **Kaam**: Authentication aur authorization ke liye.  
   - **Example**: Office mein jab tu login karta hai aur system check karta hai ke tu kaun hai, Kerberos kaam karta hai.

10. **LDAP (Lightweight Directory Access Protocol) - Port 389**  
    - **Kaam**: Directory services ke liye, jaise employee details store karna.  
    - **Example**: Company ke database mein employee ka data search karna, LDAP ke through hota hai.

11. **RADIUS - Port 1812, 1813**  
    - **Kaam**: Authentication aur authorization ke liye, mostly Wi-Fi ya VPN mein.  
    - **Example**: Jab tu public Wi-Fi pe login karta hai, RADIUS check karta hai ke tu authorized hai ya nahi.

12. **DHCP (Dynamic Host Configuration Protocol) - Port 67, 68**  
    - **Kaam**: Devices ko IP address automatically deta hai.  
    - **Example**: Ghar ke Wi-Fi se connect hone pe tera phone ek IP address leta hai, yeh DHCP ka kaam hai.

13. **RDP (Remote Desktop Protocol) - Port 3389**  
    - **Kaam**: Remote computer ko access karne ke liye.  
    - **Example**: Jab tu ghar se office ke computer ko control karta hai, RDP use hota hai.

14. **NNTP (Network News Transfer Protocol) - Port 119**  
    - **Kaam**: Newsgroups (online discussion groups) ko access karne ke liye.  
    - **Example**: Purane zamane mein online forums ke liye use hota tha.

15. **RPC (Remote Procedure Call) - Port 135, 137-139**  
    - **Kaam**: Remote computer pe commands chalaane ke liye.  
    - **Example**: Ek software jo server pe kuch run karta hai, RPC use karta hai.

16. **Ident (Identification Protocol) - Port 113**  
    - **Kaam**: User processes ko identify karne ke liye.  
    - **Example**: Server check karta hai ke kaun sa user connected hai.

17. **ICMP (Internet Control Message Protocol) - Port 0-255**  
    - **Kaam**: Network issues ko troubleshoot karne ke liye.  
    - **Example**: Jab tu “ping” command use karta hai, ICMP kaam karta hai.

18. **IGMP (Internet Group Management Protocol) - Port 0-255**  
    - **Kaam**: Multicasting ke liye, jaise ek hi data multiple devices ko bhejne ke liye.  
    - **Example**: Live streaming mein jab ek video sab ko ek saath jati hai.

19. **Oracle DB Listener - Port 1521/1526**  
    - **Kaam**: Oracle database se client requests lene ke liye.  
    - **Example**: Jab tu Oracle database se data mangta hai, yeh listener handle karta hai.

20. **Ingres Lock - Port 1524**  
    - **Kaam**: Ingres database ke liye, jo bade commercial apps mein use hota hai.  
    - **Example**: Bade systems jaise banking apps mein data store karna.

21. **Squid Web Proxy - Port 3128**  
    - **Kaam**: Web requests ko cache karke server ko fast karta hai.  
    - **Example**: Office mein internet speed badhane ke liye proxy use hota hai.

22. **SCP (Secure Copy Protocol) - Port 22**  
    - **Kaam**: Files ko securely systems ke beech copy karne ke liye.  
    - **Example**: Jab tu SSH ke through files transfer karta hai.

23. **SIP (Session Initiation Protocol) - Port 5060**  
    - **Kaam**: VoIP calls (jaise Skype) ke liye sessions banata hai.  
    - **Example**: WhatsApp video call ke liye SIP kaam karta hai.

24. **SOAP (Simple Object Access Protocol) - Port 80, 443**  
    - **Kaam**: Web services ke liye data exchange.  
    - **Example**: Online payment systems mein SOAP use hota hai.

25. **SSL (Secure Socket Layer) - Port 443**  
    - **Kaam**: Files ko securely transfer karne ke liye.  
    - **Example**: Jab tu https:// wali website use karta hai, SSL security deta hai.

26. **TCP Wrappers - Port 113**  
    - **Kaam**: Network access ko control karta hai.  
    - **Example**: Server decide karta hai ke kaun connect kar sakta hai.

27. **ISAKMP - Port 500**  
    - **Kaam**: VPN connections ke liye security manage karta hai.  
    - **Example**: Jab tu VPN se office network join karta hai.

28. **Microsoft SQL Server - Port 1433**  
    - **Kaam**: Microsoft SQL database se client connections ke liye.  
    - **Example**: Jab tu company ke database se data leta hai.

29. **KINK (Kerberized Internet Negotiation of Keys) - Port 892**  
    - **Kaam**: Authentication aur authorization ke liye.  
    - **Example**: Secure systems mein login ke liye.

30. **OSPF (Open Shortest Path First) - Port 89**  
    - **Kaam**: Network mein data ke liye shortest route dhundta hai.  
    - **Example**: Bade networks mein routers ke beech communication.

31. **PPTP (Point-to-Point Tunneling Protocol) - Port 1723**  
    - **Kaam**: VPN connections banane ke liye.  
    - **Example**: Jab tu remote server se connect karta hai.

32. **REXEC (Remote Execution) - Port 512**  
    - **Kaam**: Remote computer pe commands chalaane ke liye.  
    - **Example**: Server pe koi script run karna.

33. **RLOGIN (Remote Login) - Port 513**  
    - **Kaam**: Remote computer pe interactive session start karta hai.  
    - **Example**: Jaise SSH ke purane version mein login karna.

34. **X Window System (X11) - Port 6000**  
    - **Kaam**: Networked computers ke liye GUI deta hai.  
    - **Example**: Remote desktop pe graphical interface dikhana.

35. **DB2 (Relational Database Management System) - Port 50000**  
    - **Kaam**: Data store, retrieve aur manage karta hai, bade systems ke liye.  
    - **Example**: Banking ya CRM systems mein data handling.

---

### **UDP (User Datagram Protocol) Kya Hai?**  
UDP ek **connectionless protocol** hai, yani yeh data bhejne se pehle koi virtual connection nahi banata. Bas data packets ko destination pe bhej deta hai, bina yeh check kiye ke woh wahan pohanche ya nahi.  

**Example**: Jab tu YouTube pe video stream karta hai, toh video data UDP ke through tujhe milta hai. Kyunki video mein agar thodi si data loss ho jaye, toh bhi chal jata hai, lekin speed zaroori hai. Agar kuch packets miss ho gaye, toh video quality pe zyada farq nahi padta. Isliye UDP **TCP se fast** hai, lekin **kam reliable** hai kyunki yeh guarantee nahi deta ke sab packets pohancheinge.

### **Common UDP Protocols aur Unka Kaam**  
Yeh list hai un protocols ki jo UDP ke saath kaam karte hain, unke ports aur kaam ke saath:

1. **DNS (Domain Name System) - Port 53**  
   - **Kaam**: Domain names (jaise www.google.com) ko IP addresses mein convert karta hai.  
   - **Example**: Jab tu browser mein URL daalta hai, DNS usko IP address mein badalta hai taake website load ho sake.

2. **TFTP (Trivial File Transfer Protocol) - Port 69**  
   - **Kaam**: Files transfer karne ke liye, lekin simple aur lightweight tarike se.  
   - **Example**: Chhote devices jaise routers mein firmware update ke liye TFTP use hota hai.

3. **NTP (Network Time Protocol) - Port 123**  
   - **Kaam**: Network mein computers ke clocks ko sync karta hai.  
   - **Example**: Tera phone aur laptop ek hi time show karein, yeh NTP ka kaam hai.

4. **SNMP (Simple Network Management Protocol) - Port 161**  
   - **Kaam**: Network devices ko monitor aur manage karta hai.  
   - **Example**: Office mein routers ya switches ke status ko check karna.

5. **RIP (Routing Information Protocol) - Port 520**  
   - **Kaam**: Routers ke beech routing information share karta hai.  
   - **Example**: Network mein data ka shortest path dhundne ke liye.

6. **IKE (Internet Key Exchange) - Port 500**  
   - **Kaam**: Secure communication ke liye keys exchange karta hai, mostly VPNs mein.  
   - **Example**: Jab tu VPN use karta hai, IKE secure connection banata hai.

7. **BOOTP (Bootstrap Protocol) - Port 68**  
   - **Kaam**: Network mein devices ko start karne ke liye IP address deta hai.  
   - **Example**: New device ko network se connect karne ke liye.

8. **DHCP (Dynamic Host Configuration Protocol) - Port 67**  
   - **Kaam**: Devices ko automatically IP addresses deta hai.  
   - **Example**: Ghar ke Wi-Fi se tera phone IP address leta hai, yeh DHCP ka kaam hai.

9. **TELNET - Port 23**  
   - **Kaam**: Text-based remote access ke liye.  
   - **Example**: Purane zamane mein servers ko remotely control karne ke liye use hota tha (ab kam use hota hai).

10. **MySQL - Port 3306**  
    - **Kaam**: Open-source database management system hai.  
    - **Example**: Websites jaise WordPress apna data MySQL mein store karti hain.

11. **TS (Terminal Server) - Port 3389**  
    - **Kaam**: Microsoft Windows ke liye remote access protocol.  
    - **Example**: Remote Desktop se office ke PC ko ghar se control karna.

12. **NetBIOS Name (netbios-ns) - Port 137**  
    - **Kaam**: Windows systems mein NetBIOS names ko IP addresses mein convert karta hai.  
    - **Example**: Local network mein computers ke naam resolve karna.

13. **Microsoft SQL Server Browser (ms-sql-m) - Port 1434**  
    - **Kaam**: Microsoft SQL Server ke client connections ko manage karta hai.  
    - **Example**: Jab tu company ke SQL database se data leta hai.

14. **UPnP (Universal Plug and Play) - Port 1900**  
    - **Kaam**: Devices ko network pe ek doosre se discover aur communicate karne deta hai.  
    - **Example**: Smart TV ya game console ka automatic setup.

15. **PostgreSQL - Port 5432**  
    - **Kaam**: Object-relational database management system.  
    - **Example**: Bade apps jaise financial systems mein data store karna.

16. **VNC (Virtual Network Computing) - Port 5900**  
    - **Kaam**: Graphical desktop sharing ke liye.  
    - **Example**: Remote computer ki screen ko apne device pe dekhna aur control karna.

17. **X Window System (X11) - Port 6000-6063**  
    - **Kaam**: Unix-like systems ke liye GUI deta hai.  
    - **Example**: Linux servers pe graphical interface remotely dikhana.

18. **Syslog - Port 514**  
    - **Kaam**: System ke log messages collect aur store karta hai.  
    - **Example**: Server ke errors ya activities ko track karna.

19. **IRC (Internet Relay Chat) - Port 194**  
    - **Kaam**: Real-time text messaging (chat) ke liye.  
    - **Example**: Purane online chat rooms ke liye use hota tha.

20. **OpenPGP - Port 11371**  
    - **Kaam**: Data aur communication ko encrypt aur sign karta hai.  
    - **Example**: Secure email ya file sharing ke liye.

21. **IPsec (Internet Protocol Security) - Port 500**  
    - **Kaam**: Secure aur encrypted communication deta hai, mostly VPNs mein.  
    - **Example**: Jab tu VPN se secure connection banata hai.

22. **IKE (Internet Key Exchange) - Port 11371**  
    - **Kaam**: Encryption keys manage karta hai secure communication ke liye.  
    - **Example**: VPN ya secure apps ke liye.

23. **XDMCP (X Display Manager Control Protocol) - Port 177**  
    - **Kaam**: X11 system pe remote login ke liye.  
    - **Example**: Linux system pe remotely GUI access karna.

### **Kyun Seekhein?**  
UDP aur yeh protocols network ka important hissa hain. UDP fast hai, isliye streaming, gaming, ya DNS jaise kaamon mein use hota hai jahan thodi si data loss se farq nahi padta. Inko samajhna tujhe network ke kaam ko behtar samajhne mein madad karega, aur tu issues jaldi solve kar sakega. Har protocol ka apna role hai, aur inko step-by-step seekh ke tu network mein pro ban sakta hai!

---

### **ICMP (Internet Control Message Protocol) Kya Hai?**  
ICMP ek protocol hai jo devices ko ek doosre se baat karne mein madad karta hai, khas kar error reporting aur status information ke liye. Yeh devices ke beech messages bhejta hai, jo errors ya status batate hain.

#### **ICMP Requests**  
Request ek aisa message hai jo ek device doosre device ko koi information mangne ya koi action karne ke liye bhejta hai.  
- **Example**: **Ping request** – Yeh check karta hai ke do devices ke beech connection hai ya nahi. Jab ek device ping bhejta hai, toh doosra device **ping reply** bhejta hai.

#### **ICMP Messages**  
ICMP ke messages do tarah ke hote hain: request ya reply. Aur bhi kaafi messages hote hain, jaise:  
1. **Echo Reply**: Ping request ka jawab hota hai.  
2. **Destination Unreachable**: Jab packet apne destination tak nahi pohanchega, yeh message bheja jata hai.  
3. **Redirect**: Router yeh message bhejta hai jab device ko kisi doosre router pe packet bhejne ki zarurat ho.  
4. **Time Exceeded**: Jab packet ko destination tak pohanchna mein bohot time lag jaye.  
5. **Parameter Problem**: Jab packet ke header mein koi issue ho.  
6. **Source Quench**: Jab ek device ko packets bohot tezi se mil rahe hon aur woh handle na kar sake.

#### **ICMP ke Versions**  
- **ICMPv4**: Yeh IPv4 ke liye hai aur sabse zyada use hota hai.  
- **ICMPv6**: Yeh IPv6 ke liye hai aur isme extra features hain.

#### **Time-To-Live (TTL)**  
TTL ek field hai jo packet ke lifetime ko limit karta hai. Har baar jab packet router se guzarta hai, TTL ki value 1 kam ho jati hai. Agar TTL 0 ho jaye, toh router packet ko discard kar deta hai aur **Time Exceeded** message bhejta hai.  
- **Example**: Agar ek packet ka TTL 10 hai aur woh 5 routers se guzarta hai, toh destination 5 hops door hai.  
- **OS Guessing**: TTL se operating system bhi guess kiya ja sakta hai:  
  - Windows: Default TTL = 128  
  - Linux/macOS: Default TTL = 64  
  - Solaris: Default TTL = 255  
  *Note*: Yeh values user badal sakta hai, isliye 100% sure nahi kiya ja sakta.

**Example**: Agar ping ka TTL 122 hai, toh shayad yeh Windows system (default 128) se hai aur 6 hops door hai.

### **VoIP (Voice over Internet Protocol) Kya Hai?**  
VoIP ek tarika hai jisme voice aur multimedia communication internet ke zariye hoti hai, jaise phone calls bina traditional phone line ke.  
- **Example**: Skype, WhatsApp, Zoom, ya Google Hangouts sab VoIP use karte hain.

#### **Common VoIP Ports**  
- **TCP/5060, TCP/5061**: **SIP (Session Initiation Protocol)** ke liye, jo VoIP ka main protocol hai.  
- **TCP/1720**: **H.323 protocol** ke liye, lekin yeh SIP se kam use hota hai.

#### **SIP (Session Initiation Protocol)**  
SIP ek signaling protocol hai jo video, voice, messaging, ya doosre real-time sessions ko start, manage, aur end karta hai. Yeh endpoints (devices) ke beech requests aur methods use karta hai. Common SIP methods:  
1. **INVITE**: Ek session shuru karta hai ya doosre device ko invite karta hai.  
2. **ACK**: INVITE request ko confirm karta hai.  
3. **BYE**: Session ko end karta hai.  
4. **CANCEL**: Pending INVITE request ko cancel karta hai.  
5. **REGISTER**: SIP user ko server ke saath register karta hai.  
6. **OPTIONS**: SIP server ya user ke capabilities (jaise media types) ke baare mein info mangta hai.

#### **SIP aur Security Risk**  
SIP ke zariye attackers user information nikaal sakte hain, jaise:  
- **SIP OPTIONS Request**: Yeh server ya user ke capabilities check karta hai, jaise supported media ya codecs. Isse attackers user availability ya services ke baare mein pata laga sakte hain, jo brute-force attacks ke liye use ho sakta hai.

#### **SEPxxxx.cnf File**  
Yeh ek configuration file hai jo **Cisco Unified Communications Manager** (pehle Cisco CallManager) use karta hai. Isme Cisco IP Phone ke settings hote hain, jaise phone model, firmware version, aur network details.  
- **Example**: Jab tu office mein Cisco IP Phone use karta hai, yeh file uske settings define karta hai.
 
ICMP network troubleshooting ka hero hai. Yeh errors ko samajhne aur fix karne mein madad karta hai, jaise ping ya traceroute se. VoIP seekhna zaroori hai kyunki aaj kal communication internet pe shift ho chuki hai, aur SIP jaise protocols uska base hain. Inko samajh ke tu network issues solve kar sakta hai, VoIP systems ko secure rakh sakta hai, aur ek pro ban sakta hai.  

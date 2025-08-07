**Nmap kya hai?**  
Nmap (Network Mapper) ek free tool hai jo networks ko scan karta hai. Ye C, C++, Python, aur Lua mein bana hai. Is se tum ye pata laga sakte ho ke network mein kaun se devices (hosts) active hain, un pe kaun se services aur apps chal rahe hain (naam aur version ke saath), aur kon sa operating system (OS) chal raha hai. Saath hi, ye firewall, packet filters, ya intrusion detection systems (IDS) ke settings bhi check kar sakta hai.

---

**Nmap ka use kahan hota hai?**  
Network admins aur IT security wale isko bohot use karte hain. Ye in cheezon ke liye kaam aata hai:  
- Network ki security check karna.  
- Penetration testing (hacking ka simulation).  
- Firewall aur IDS ke settings dekhna.  
- Network mapping (network ka layout samajhna).  
- Open ports dhoondna.  
- Weaknesses (vulnerabilities) check karna.

---

**Nmap kaise kaam karta hai?**  
Nmap ke paas bohot se scanning types hain, jo alag-alag results dete hain. Ye kuch main scanning techniques hain:  
1. **Host Discovery:** Dekhna ke kaun se devices network pe hain.  
2. **Port Scanning:** Check karna ke kaun se ports open hain.  
3. **Service Enumeration:** Ports pe chal rahi services ka pata lagana.  
4. **OS Detection:** Target ka operating system aur version maloom karna.  
5. **Nmap Scripting Engine:** Services ke saath interact karne ke liye scripts chalana.

---

**Nmap ka syntax:**  
Nmap ka command simple hai:  
```
nmap <scan types> <options> <target>
```  
Misaal ke taur pe: `nmap -sS 192.168.1.1`  
Yahan `-sS` ek scan type hai, aur `192.168.1.1` target ka IP address hai.

---

**Scan types:**  
Nmap ke bohot se scan types hain, kuch common yeh hain:  
- **-sS (TCP SYN Scan):** Ye default aur bohot fast hai. Ye ek SYN packet bhejta hai aur three-way handshake complete nahi karta. Agar target se SYN-ACK aaye, toh port open hai. Agar RST aaye, toh port closed hai. Agar koi response na aaye, toh port “filtered” hai (firewall ke wajah se).  
- **-sU:** UDP ports scan karta hai.  
- **-sN/sF/sX:** TCP Null, FIN, ya Xmas scans (stealth scans).  
- **-sO:** IP protocol scan.  

**Misaal:**  
Yeh dekho ek TCP SYN scan ka example:  
```
sudo nmap -sS localhost
```
**Output:**  
```
Starting Nmap 7.80
Nmap scan report for localhost (127.0.0.1)
Host is up (0.000010s latency).
Not shown: 996 closed ports
PORT     STATE SERVICE
22/tcp   open  ssh
80/tcp   open  http
5432/tcp open  postgresql
5901/tcp open  vnc-1
Nmap done: 1 IP address (1 host up) scanned in 0.18 seconds
```
Isme dekho, 4 ports open hain:  
- Port 22 (SSH)  
- Port 80 (HTTP)  
- Port 5432 (PostgreSQL)  
- Port 5901 (VNC)  

---

**Kyun zaroori hai?**  
Nmap se tumhe target ke baare mein bohot si information milti hai, jaise open ports aur services. Ye info tumhein attack ke liye weak points dhoondne mein madad karti hai. Lekin yaad rakho, tools ke saath-saath apni knowledge bhi use karo, kyunki sirf tool hi kaafi nahi.

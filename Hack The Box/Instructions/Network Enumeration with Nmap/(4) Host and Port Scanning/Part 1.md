# **Host aur Port Scanning – Notes**

---

## **Host ka Matlab**

Host ka matlab hai koi bhi device ya server jo network pe connected ho — yeh ek website ka server, kisi office ka computer, ya teri apni machine bhi ho sakta hai.

* IP address → host ka location hota hai.
* Domain → host ka naam hota hai.

Jab hum browser me website ka domain dalte hain aur woh load ho jata hai, iska matlab HTTP/HTTPS port (80/443) open hai aur web server chal raha hai.
Ping command ka kaam hai poore host ka **alive status** check karna, sirf website ka nahi.

---

## **ICMP aur Ping**

* **ICMP (Internet Control Message Protocol)** ek messenger hai jo devices ko network ka status batata hai — packet deliver hua ya nahi, koi error aayi ya nahi.
* **Ping command** ICMP Echo Request bhejta hai, dusra device Echo Reply bhejta hai.
* Reply aaye → host alive hai.
* Reply na aaye → ya toh host down hai, ya firewall ICMP block kar raha hai.

💡 **Example:**
Google ko ping karo:

```bash
ping google.com
```

Reply aaya → Google alive hai.
Reply nahi aaya → Google down ho sakta hai (rare case) ya ICMP block hai.

Security-focused companies (jaise banks, govt sites) ICMP block karte hain taake attacker easily detect na kare ke host alive hai.

---

## **Nmap ka Main Purpose**

Nmap ka main kaam hai:

1. Host alive check karna.
2. Open ports detect karna.
3. Ports ki services aur versions identify karna.
4. Operating system detect karna.

**Hacker point of view:**

* Agar open port ka version outdated hai → uska exploit mil sakta hai.
* Agar updated hai → phir bhi misconfiguration ya logical bug mil sakta hai.

💡 **Example:** Apache latest version chal raha hai par directory listing open hai → sensitive files mil sakti hain.

---

## **Port States (Nmap ke mutabiq)**

1. **Open** → Darwaza khula hai, service chal rahi hai (e.g., HTTP, SSH).

   * Hacker ke liye entry point.
   * Example: Port 22 open → SSH brute force try kar sakte ho.
2. **Closed** → Darwaza band hai, service chal nahi rahi.

   * Entry point kam hota hai.
3. **Filtered** → Firewall block kar raha hai, Nmap confirm nahi kar sakta open hai ya closed.

   * Hacker ke liye challenge → firewall bypass techniques use karni padti hain.
4. **Unfiltered** → Port accessible hai, par status clear nahi (sirf TCP-ACK scan me hota hai).
5. **Open|Filtered** → Response nahi mila, shayad firewall protect kar raha hai.
6. **Closed|Filtered** → Sirf IP ID idle scan me hota hai, status clear nahi.

---

## **Filtered Ports ka Faida Admin ke Liye**

* Attackers ko confuse karna.
* Possible attacks ko block karna before they reach service.

💡 **Example:** Agar port 80 filtered hai, attacker confirm nahi kar sakta ke web server chal raha hai ya nahi.

---

## **Scanning Commands Examples**

* **Top 1000 TCP ports (default root user)**:

```bash
nmap -sS target.com
```

* **All ports**:

```bash
nmap -p- target.com
```

* **Specific ports**:

```bash
nmap -p 22,80,443 target.com
```

* **Range scan**:

```bash
nmap -p 80-445 target.com
```

* **Top 10 ports**:

```bash
nmap --top-ports=10 target.com
```

* **Skip ICMP ping**:

```bash
nmap -Pn target.com
```

---

## **Filtered Ports Bypass Techniques**

* **Decoy scan**:

```bash
nmap -D RND:10 target.com
```

* **Fragment packets**:

```bash
nmap -f target.com
```

* **Source port trick**:

```bash
nmap --source-port 53 target.com
```

* **Idle scan**:

```bash
nmap -sI zombie_ip target.com
```

💡 In techniques ka kaam firewall ko confuse karna hai taake filtered ports ka status pata chal sake.

---

## **Real-Life Hacker Flow**

1. Ping se check karo host alive hai ya nahi. Agar ICMP block hai toh `-Pn` use karo.
2. Port scan karo (range ya top ports).
3. Open ports ki services aur versions identify karo.
4. Outdated version ka exploit dhundo (Exploit-DB, searchsploit).
5. Agar updated hai → misconfigurations aur logic flaws test karo.
6. Agar filtered ports mile → firewall evasion techniques lagao.

---

💬 **Summary**

* Open port = entry point for hacker.
* Closed port = kam attack surface.
* Filtered port = firewall ka kaam.
* Nmap sirf outdated version dhoondne ka tool nahi hai — yeh tumhare liye **map** banata hai ki attack kahan se start karna hai.


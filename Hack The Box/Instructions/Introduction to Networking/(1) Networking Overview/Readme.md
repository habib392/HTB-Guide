# 🔐 Networking & Security Guide –

---

## 📡 Networking ka Asal Matlab

Networking ka matlab hai 2 ya zyada computers ka ek dosray se baat karna. Yeh baat alag alag tareeqon se ho sakti hai jaise:

* **Topologies**: Star, Mesh, Tree waghera
* **Mediums**: Ethernet cable, fiber, wireless
* **Protocols**: TCP, UDP, IPX, etc.

Ek security expert ko networking ka basic samajhna bohat zaroori hai. Kyun? Kyun ke agar network khamoshi se fail ho gaya, toh tumhara pentest bhi fail ho sakta hai bina kisi signal ke.

---

## 🏠 Flat Network vs Segmented Network

### 🧱 Flat Network:

Ek simple flat network banana asaan hai, lekin yeh sirf operable hota hai — secure nahi.

**Example:** Ghar banaya, sirf ek darwaza lock lagaya — bas! Agar koi chhup ke deewar phandh le, koi nahi dekh paayega. Jaisy aik company main network hai 200 computers ka or sub apas main connected hai agar aik computer main malware aaya too sub infect hoo jayein gy

### 🔐 Segmented Network:

Chhoti chhoti networks (subnets) banao, har ek ke darmiyan **ACLs (Access Control Lists)** lagao. Yeh multiple barriers banata hai. Or switches main VLANs bhi lgao yani aik switch sy 50 computers connected hai too VLANs lagamy ky baad woh 5 groups main divide hoo skty hain har group main 10 computer for security purpose.

**Real Life Example 1:** Printer network agar server se HTTP pe baat kar raha hai — yeh abnormal hai. ACL se block kar sakte ho.

**Real Life Example 2:** Har network ka map banao, documentation rakho — jaise ghar ke chaaron taraf lights lagana. Sab kuch dikhayi deta hai.

**Real Life Example 3:** IDS (Snort/Suricata) lagao — yeh bushes ki tarah kaam karti hain jo attacker ko scan karne pr alert bhejta hai network team ko example nmap, brute forcing sy scanning waghaira. Agar printer port scan kar raha hai — red alert!

### 🚫 Problem:

Agar sab kuch ek hi /24 flat subnet mein hai (192.168.1.0/24), toh printer ko isolate karna mushkil ho jaata hai. Woh DHCP se IP le leta hai aur sab network devices se baat kar sakta hai.

---

## 🕵️‍♂️ Pentester ki Ghalti ka Waqia

Ek pentester ne IP set ki: `10.20.0.252/24`
Lekin server, client, DC sab `/25` subnet par thay.

* DC: 10.20.0.10/25
* Client: 10.20.0.200/25

Pentester sirf client network mein ghus saka, aur DC tak nahi pohch saka.

**Real Issue**: Network ki samajh nahi thi.

### 📘 Lesson:

Hamesha subnet mask verify karo — `/24` aur `/25` ka farq mission fail karwa sakta hai.

---

## 🌐 Internet & Networking: Post Office Example

Imagine karo ke tu ghar se kisi company ki website access kar raha hai:

* Tu website ka **URL** type karta hai ([https://www.site.com/info](https://www.site.com/info))
* Yeh browser ko batata hai kahan jana hai
* Yeh **FQDN** (like [www.site.com](http://www.site.com)) se **IP address** find karta hai using DNS
* Packet pehli post office (router) se nikalta hai ISP ke paas
* ISP DNS se IP address find karta hai
* Phir packet destination web server tak jata hai

**Real World Mapping:**

* Ghar ka router = Local post office
* ISP = Main post office
* DNS = Address book
* IP = Final address
* URL = Room, floor, employee tak location

---

## 🛡️ Company Network Design – Secure Karna Seekho

### ✅ DMZ for Web Server:

Web server ko **DMZ** mein rakho (isolated zone). Yeh public-facing server hota hai, toh risk zyada hota hai. Isko baqi internal servers se alag rakho.

### ✅ Workstation Network:

Workstations alag hone chahiye, ideally **ek dusray se baat bhi na kar sakein**. Agar workstation aur server same network mein hain toh MITM attacks ka risk badh jaata hai.

### ✅ Admin Network:

Routers & switches ko **Admin network** mein rakho. Yeh OSPF jaise protocol sniff hone se bachata hai.

### ✅ IP Phones:

Inko bhi alag network do. Latency low chahiye hoti hai aur security bhi important hai (voice sniffing se bacho).

### ✅ Printers:

Printers ko secure karna mushkil hota hai. Unko bhi alag network mein rakho.

**Real Example:**
COVID ke time ek pentester ne printer mein reverse shell daala, aur printer company ko bhej diya — jese gift. Printer connect hota hi shell mil gaya.

**Why it worked?**

* Printer internet se connect ho sakta tha ❌
* Workstation ne printer ko port 445 pe access kiya ❌
* Printer ne connection initiate kiya workstation se ❌

**Agar secure network hota toh kya hota?**

* Printer ko internet access nahi milta
* Port restrictions hoti
* Internal firewall/printer segmentation hota

---

## 🧠 Final Summary

| Topic             | Samjhaani                                            |
| ----------------- | ---------------------------------------------------- |
| Flat Network      | Sab devices ek hi network mein – risky               |
| Segmented Network | Har device/group ka apna subnet – secure             |
| ACLs              | Har subnet pe entry/exit control rules               |
| IDS/IPS           | Jaise Snort – suspicious activity detect karta hai   |
| Subnetting        | /25, /26 – network ko chhoti units mein divide karna |
| DMZ               | Web server ko public exposure se alag rakhna         |
| Printer Network   | Printer ko isolate karna for security                |
| URL/FQDN          | URL detail batata hai, FQDN address batata hai       |
| Router/ISP/DNS    | Data delivery ka post office system                  |

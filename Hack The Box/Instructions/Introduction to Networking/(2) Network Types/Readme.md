# 💡 **Network Types**

---

## 🔸 **1. Networks kyun alag-alag hotay hain?**

Har network ka **size**, **area**, aur **usage** alag hota hai. Is liye experts ne kuch **types** aur **topologies** design ki hain jinki madad se hum jaan sakte hain ke network chhota hai ya bara, personal hai ya global.

---

## 🔸 **2. Common Terms (Real World mein use hone wali)**

| Network Type | Asaan Matlab            | Real Example                 |
| ------------ | ----------------------- | ---------------------------- |
| **WAN**      | Internet                | Poora world connect hai      |
| **LAN**      | Local Network           | Office, Ghar ka network      |
| **WLAN**     | Wireless LAN            | Wi-Fi wala network           |
| **VPN**      | Virtual Private Network | Do networks ka door se jurna |

---

### ✅ **WAN (Wide Area Network)**

* Poora **Internet** basically ek WAN hai.
* Har company ka apna **internal WAN** bhi ho sakta hai (Intranet).
* WAN public IPs use karta hai (jo RFC1918 range mein nahi hoti).
* WAN main **BGP protocol** use hota hai.

**💡 Tip:** Jab tum kisi server ka IP dekho, agar woh 10.x ya 192.168.x nahi hai, to woh WAN ka IP hai.

---

### ✅ **LAN / WLAN (Local / Wireless Local Area Network)**

* **LAN:** Wires se connect devices (ghar/office).
* **WLAN:** Wi-Fi se connect devices (lekin wohi LAN ka wireless version hai).
* Dono usually **private IPs** use karte hain:

  * 192.168.x.x
  * 10.x.x.x
  * 172.16.x.x

**💡 Tip:** Jab tum kisi network mein ho aur IP 192.168 ya 10 se start ho, to yeh internal/local network hai — ismein `nmap`, `netdiscover` etc. use hotay hain.

---

### ✅ **VPN (Virtual Private Network)**

VPN ka kaam yeh hota hai ke tum door beth kar bhi kisi network mein **"physically maujood"** feel karo.

#### 🧱 Site-to-Site VPN

* Router ya Firewall dono sides par hotay hain.
* **Example:** Company ke Lahore aur Karachi ke offices ek VPN se connected.

#### 🧑‍💻 Remote Access VPN

* Client ka computer virtual interface banata hai (e.g. HTB labs ka `tun0`).
* **Split-Tunnel VPN:** Sirf kuch IPs VPN se guzarti hain, baaki Internet local connection se chalta hai.

#### 🌐 SSL VPN

* Web browser ke andar chalne wali VPN.
* **Example:** HTB Pwnbox — browser ke zariye pura hacking OS chal jata hai.

---

## 🔸 **3. Book Terms (Theory wali, exams ke liye important)**

| Network Type   | Asaan Matlab                        |
| -------------- | ----------------------------------- |
| **GAN**        | Global Network (poori duniya)       |
| **MAN**        | City-level network                  |
| **PAN / WPAN** | Personal ya Bluetooth based network |

---

### ✅ **GAN (Global Area Network)**

* Poora **Internet** bhi ek GAN hai.
* Companies bhi apna international private GAN banati hain.
* Satellite aur undersea fiber optic cables se connect hotay hain.

---

### ✅ **MAN (Metropolitan Area Network)**

* Sheher ke andar multiple LANs ko jorna.
* Fast aur reliable hota hai — zyada tar fiber optic se connected hota hai.
* **Example:** Ek company ke sheher ke 4 branches ek MAN se connected hain.

---

### ✅ **PAN / WPAN (Personal Area Network / Wireless PAN)**

* Chhota network, sirf ek shakhs ke devices ke darmiyan.
* Wired version = PAN (e.g. USB se mobile-PC).
* Wireless version = WPAN (e.g. Bluetooth headphones).
* Bluetooth network ka special naam: **Piconet**

**💡 IoT Tip:** Zigbee, Z-Wave jaise protocols smart homes mein use hotay hain aur inse security holes nikalte hain — pen testers ke liye mauqa.

---

## 🔸 **4. Penetration Testing Relevance**

| Concept      | Pen Testing mein Use                       |
| ------------ | ------------------------------------------ |
| LAN          | Local devices discovery, scanning          |
| WAN          | Public targets, web apps                   |
| VPN          | Remote lab access, like HTB                |
| WLAN         | Wi-Fi hacking, packet sniffing             |
| WPAN         | IoT devices attack vector                  |
| Split Tunnel | Lab access without affecting your Internet |

---

## 🔸 **5. Bonus Knowledge: IP Address Ranges**

| IP Range                    | Use          |
| --------------------------- | ------------ |
| `10.0.0.0/8`                | Private LAN  |
| `172.16.0.0/12`             | Private LAN  |
| `192.168.0.0/16`            | Private LAN  |
| Public IPs (e.g. `8.8.8.8`) | WAN/Internet |

---

### 🧠 **Root Philosophy:**

> "Elon Musk ne kaha ke har cheez ko first principles se samajho — toh agar aapko ek IP diya gaya hai ya koi system test karna hai, sabse pehle uska network samjho. Local hai ya global? Secure hai ya nahi? Iska base logic samjho — phir exploit karo."

---

### ✅ **Yeh sab hum ne discuss kiya:**

1. Network types (WAN, LAN, VPN, etc.)
2. Har type ka real-world use
3. Private vs Public IP ka difference
4. VPNs kaam kaise karti hain (Remote, Site-to-Site, SSL)
5. Book terms (GAN, MAN, PAN)
6. Pen testing relevance of each type


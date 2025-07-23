## 💻 IP Address, MAC Address, Broadcasting & Classes (Meri Zubaan Mein)

---

### 🔹 **MAC Address kya hota hai?**

Har device ka network card (jaise Wi-Fi ya LAN) ka ek **unique ID** hota hai, jise kehte hain **MAC Address**.
Ye sirf **local network** mein use hota hai — jaise ghar ke andar Wi-Fi se connect devices.

> Soch le MAC address = Building ke andar ka **Flat Number**

---

### 🔹 **IP Address kya hota hai?**

Jab tu internet pe ya kisi door ke device se connect hota hai, toh MAC kaam nahi karta — uske liye chahiye **IP address**.
IP address ek **unique digital address** hota hai jo data ko sahi jagah deliver karne mein help karta hai.

> Soch le IP address = Us building ka **postal address** (shahar, area, street, building)

---

### 🔸 **MAC vs IP Real Example:**

| Cheez       | Example                      |
| ----------- | ---------------------------- |
| MAC Address | Flat #102                    |
| IP Address  | House #25, Street #7, Attock |

---

### 🔹 **Local Network (LAN) kya hoti hai?**

Ghar ke andar ya kisi office ke andar devices jo ek router se connect hoti hain — unka group hota hai **Local Area Network (LAN)**.
Yahan sab devices aapas mein file bhej sakti hain, printer use kar sakti hain ya games khel sakti hain.

---

### 🔹 **Broadcasting kya hoti hai?**

**Broadcasting** ka matlab hai ek hi message ko ek saath network ke sab devices ko bhejna.
Jaise loudspeaker pe kehna:

> “Bijli 10 baje ja rahi hai sab sun lo!”

Network mein agar tu message `192.168.1.255` pe bhejta hai, toh sab devices (jo is range mein hain) woh message receive karti hain.

---

### 🔹 **IP Broadcasting Penetration Testing Mein**

* Tu jab `nmap`, `netdiscover`, `arp-scan` jaise tools use karta hai toh yeh **broadcast ARP requests** bhejte hain.
* Isse tu identify karta hai network ke sab devices ko — unka IP & MAC milta hai.

---

### 🔹 **IPv4 Structure kya hai?**

IPv4 ek **32-bit address** hota hai jo 4 parts (octets) mein divide hota hai.
Har part: 0 se 255 tak hota hai.

**Example:**

* Binary: `01111111.00000000.00000000.00000001`
* Decimal: `127.0.0.1`

---

### 🔹 **IP Address ka Distribution**

IP do parts mein hoti hai:

* **Network Part** → Jo kis network ka hai
* **Host Part** → Us network ke andar kis device ka hai

### 🔸 Ghar mein:

* Router **Host Part** assign karta hai

### 🔸 Internet pe:

* **IANA** network part assign karta hai

---

### 🔹 **IP Address ki Classes (Old System)**

| Class | Range                 | Devices Allowed | Use             |
| ----- | --------------------- | --------------- | --------------- |
| A     | 1.0.0.0 – 127.x.x.x   | \~16 Million    | Big Networks    |
| B     | 128.0.0.0 – 191.x.x.x | \~65K           | Medium Networks |
| C     | 192.0.0.0 – 223.x.x.x | 254             | Small Networks  |
| D     | 224.0.0.0 – 239.x.x.x | Multicast Only  | Streaming/Games |
| E     | 240.0.0.0 – 255.x.x.x | Reserved        | Research        |

---

### 🔹 **Private IP Ranges (LAN ke liye)**

| Class | Private Range                 |
| ----- | ----------------------------- |
| A     | 10.0.0.0 – 10.255.255.255     |
| B     | 172.16.0.0 – 172.31.255.255   |
| C     | 192.168.0.0 – 192.168.255.255 |

Yeh IPs Internet pe nahi chaltin — sirf Local Network mein use hoti hain.

---

### 🔐 **Penetration Testing Mein Faida:**

* 🧠 Tu IP range dekh ke andaza laga sakta hai ke yeh local network hai ya internet ka public network
* 🎯 Broadcast aur ARP request se tu sab devices ka IP/MAC nikaal sakta hai
* 🕵️ MAC spoofing se access le sakta hai jahan MAC filtering lagi ho
* 🧱 IP spoofing se tu fake source address se attacks kar sakta hai
* 🚫 Broadcast storm se tu network slow ya down bhi kar sakta hai (DoS style)

---

## ✅ Summary:

**MAC address** andar ka flat number hai,
**IP address** building ka postal address hai,
**Broadcasting** mohallay ke loudspeaker jaisa hai,
**Local Network** ghar ya office ke andar ka network hai,
aur **IP Classes** tere network recon ka map samajhne mein madad karti hain.

---

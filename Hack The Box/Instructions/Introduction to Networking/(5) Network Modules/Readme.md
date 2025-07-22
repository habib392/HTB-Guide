### 🔌 **Networking Models Kya Hain?**

Internet pe jab 2 devices (jaise tera mobile aur server) aapas mein data bhejte hain, toh yeh **kuch rules aur layers ke zariye** hota hai. Yeh layers ka system 2 models se samjha jaata hai:

1. **OSI Model** (7 layers)
2. **TCP/IP Model** (4 layers)

---

### 📚 **OSI Model (7 Layers)**

OSI ka full form hai **Open Systems Interconnection**. Is model mein communication ko **7 chhoti-chhoti layers** mein divide kiya gaya hai — har layer ka apna kaam hai:

1. **Application** – User apps (jaise browser)
2. **Presentation** – Data format banana
3. **Session** – Connection manage karna
4. **Transport** – Data ko tukdo mein baantna (jaise TCP)
5. **Network** – Addressing aur routing (jaise IP)
6. **Data Link** – MAC address aur error check
7. **Physical** – Actual wire ya signal (jaise WiFi, cable)

Yeh model sirf **samajhne ke liye** hai — isko theory model keh lo.

---

### 🌐 **TCP/IP Model (4 Layers)**

TCP/IP model Internet pe use hota hai — real-world wale model ko yeh hi follow karta hai.

1. **Application** – Browser, email, etc.
2. **Transport** – TCP/UDP protocols
3. **Internet** – IP addressing, routing
4. **Network Access** – Hardware level data transfer

**Example:** Tu jab kisi website pe jata hai, toh data inn layers se hoke jaata hai aur aata hai — jaise **ek lehron ka silsila**.

---

### ⚔️ **OSI vs TCP/IP - Farq kya hai?**

| OSI              | TCP/IP                       |
| ---------------- | ---------------------------- |
| Theory model hai | Real-world mein use hota hai |
| 7 layers         | 4 layers                     |
| Strict protocol  | Thoda flexible hai           |

---

### 📦 **Packet Transfer kaise hota hai? (Encapsulation)**

Soch ke chal, tu website kholta hai:

* Server pe jo data hai, woh **layer by layer neeche** jaata hai (har layer apna header daalti hai — isko **Encapsulation** kehte hain).
* Fir woh data network se guzarta hua **receiver ke paas** jaata hai.
* Receiver bhi wahi layers follow karke data ko **header-wise unpack karta hai** (isko **Decapsulation** kehte hain) — aur final result teri screen pe aata hai.

---

### 🧠 **Penetration Testing mein iska kya faida?**

* **TCP/IP** model se tu **connection flow** samajh sakta hai (jaise Wireshark mein TCP Handshake).
* **OSI** model se tu har layer ka **deep analysis** kar sakta hai (packet sniffing, interception, replay, etc.).

Dono models zaroori hain jab tu **network traffic analysis** kar raha ho — jaise BurpSuite ya Wireshark mein packet dekhte waqt.

---

### 🔚 Summary:

* OSI = Theory, breakdown for analysis
* TCP/IP = Real-world use, kaam ka structure
* Encapsulation = Data mein headers chipkana
* PenTesters = Dono models ko samajhna must hai

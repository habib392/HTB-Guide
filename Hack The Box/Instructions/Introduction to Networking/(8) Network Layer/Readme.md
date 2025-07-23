## 🌐 Network Layer Kya Hai? (OSI Layer 3)

Yeh layer kaam karti hai **data ko ek jagah se doosri jagah le jaane ka**, **routing** aur **logical addressing** ka pura khel yahin hota hai.

### ⚙️ Simple Bhasha Mein:

Soch ke chal, tujhe Islamabad se Karachi koi **parcel bhejna** hai. Tu directly kisi unknown address pe nahi bhej sakta. Tu woh parcel **courier** ko deta hai — courier har sheher ke **nodes** (stations) se guzarta hai jab tak parcel manzil tak nahi pohanchta.

**Waise hi Layer 3 pe bhi data packets node se node (router to router) travel karte hain.** Har node (router) check karta hai ke next stop kya hai — isko kehte hain **routing**.

---

## 📌 Network Layer Kaam Kya Karti Hai?

1. **Logical Addressing** – Har device ko unique IP milta hai (jaise 192.168.1.1), taake pata ho data kahan bhejna hai.
2. **Routing** – Data ko ek node (router) se aglay node tak bhejna jab tak manzil mil jaye.
3. **Path Selection** – Yeh decide karta hai ke kis raaste se packet jaldi aur sahi pohanchay.

---

## 🚧 Kaam Kaise Hota Hai?

* Jab data send hota hai, yeh layer **source aur destination IP addresses** lagati hai.
* Routing tables use hoti hain jo routers ko batati hain ke data kis direction mein bhejna hai.
* Agar source aur destination alag networks mein hain, to data **routers** se guzarta hai.
* Har router us packet ko **next hop** tak forward karta hai, jab tak woh final device tak na pohanch jaye.

> ✋ Important: Jo intermediate routers hain, woh sirf **Layer 3 tak** ka data dekhte hain. Woh upper layers (jaise application layer) ko nahi dekhte.

---

## 🧪 Penetration Testing Tip:

Jab tu **network scanning** karta hai (jaise `nmap`, `traceroute`, ya `ping`), to tu actually Layer 3 ko interact kar raha hota hai. IP addresses trace karna, ya `ICMP` messages (ping) bhejna — sab yahin hota hai. Network layer ko samajhna **network pivoting** aur **firewall evasion** jaise tasks ke liye bohat zaroori hai.

---

## 🌍 Common Protocols in Network Layer:

| Protocol       | Kaam                                                                                    |
| -------------- | --------------------------------------------------------------------------------------- |
| **IPv4/IPv6**  | Logical addressing — har device ka unique address hota hai.                             |
| **IPsec**      | Secure IP communication (data ko encrypt karta hai Layer 3 pe).                         |
| **ICMP**       | Ping, traceroute — diagnostic info bhejna.                                              |
| **IGMP**       | Multicast group manage karta hai (jaise video stream ek sath multiple devices ko dena). |
| **RIP / OSPF** | Routers ko sikhaata hai ke kaunsa raasta best hai (routing protocols).                  |

---

## 🔄 Example (Real-Life Style):

Tu Lahore mein baitha hai, aur tu kisi Dubai server ko data bhej raha hai:

1. Tera data Layer 3 mein jata hai.
2. Usmein IP address lagta hai.
3. Woh data multiple routers se guzarta hai.
4. Har router Layer 3 ko check karta hai, agla router decide karta hai.
5. Data manzil tak pohanch jata hai.

> Intermediate routers sirf Layer 3 tak dekhte hain — woh teri message ki asli content nahi dekhte.

---

## 💡 Jo Doosre Logon Ka Traffic Forwards Kar Raha Hota Hai:

Woh hota hai:

* **ISP ka core router** (e.g. Nayatel/Stormfiber ka area-level router).
* **Internet Exchange Points (IXPs)**.
* **Border Gateway Routers** (international traffic ke liye).

Unhi se bohot saari users ki requests guzarti hain — **kisi ky home router** sy nahi.

---

## 🔓 Penetration Testing Tip:

Jab tu kisi network mein access le leta hai (e.g. company ka router ya gateway), aur agar tu **packet forwarding ya sniffing** allow kar le, to tu dekh sakta hai ke **kon kis IP pe request bhej raha hai**. Yeh OSI ki Layer 3 aur 4 ki game hai.

---

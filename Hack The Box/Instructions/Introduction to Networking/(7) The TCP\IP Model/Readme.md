## 🌐 TCP/IP Model Kya Hai?

TCP/IP model ka poora naam hai: **Transmission Control Protocol / Internet Protocol**
Yehi model **aaj kal ka internet** chala raha hai. Yeh bhi OSI model ki tarah **layers** par based hai, lekin ismein **sirf 4 layers** hoti hain (OSI mein 7 hoti hain).

TCP/IP model ko log **Internet Protocol Suite** bhi kehte hain.

---

## 🔢 TCP/IP Ki 4 Layers (Kaam ke Saath):

| Layer No. | Naam            | Asaan Explanation                                                                                                                       |
| --------- | --------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| 4         | **Application** | Browser, Email, WhatsApp waghera isi layer par kaam karte hain. Yeh user wale apps ko baqi layers se connect karta hai.                 |
| 3         | **Transport**   | TCP ya UDP ke zariye data ka reliable ya fast delivery ka system. TCP slow lekin safe, UDP fast lekin risk zyada.                       |
| 2         | **Internet**    | IP address aur routing ka kaam karta hai. Har packet ko uski **manzil** tak pohanchata hai.                                             |
| 1         | **Link**        | Yahan se data physical wire ya wireless signal ke zariye transmit hota hai — yani yeh OSI ki Physical + Data Link layer ka mixture hai. |

---

## 💡 Kaam Kaise Hota Hai?

* Jab tu browser mein koi website likhta hai (jaise `facebook.com`), to yeh request pehle **application layer** mein hoti hai.
* Phir data **TCP ya UDP** ke zariye **transport layer** mein jata hai.
* **Internet layer** mein IP address lagta hai — routing hoti hai.
* **Link layer** mein data wire/wifi se doosray system tak jata hai.

Yeh process dono taraf hoti hai — sender aur receiver dono mein.

---

## 🔄 TCP/IP vs OSI Model:

| TCP/IP Layer | OSI Layers Combined                  |
| ------------ | ------------------------------------ |
| Application  | Application + Presentation + Session |
| Transport    | Transport                            |
| Internet     | Network                              |
| Link         | Data Link + Physical                 |

OSI zyada detailed hai (7 layers), TCP/IP **practically zyada use hota hai** (4 layers).

---

## 📋 Important Tasks & Protocols:

| Task                     | Protocol | Kaam                                                                                                                          |
| ------------------------ | -------- | ----------------------------------------------------------------------------------------------------------------------------- |
| **Logical Addressing**   | `IP`     | Har device ko unique IP address milta hai. Yeh address packets ko sahi jagah pohanchata hai. CIDR, subnetting use hotay hain. |
| **Routing**              | `IP`     | Data har router se hota hua manzil tak jata hai. Sender ko exact location ka pata bhi na ho to bhi IP manage karta hai.       |
| **Error & Control Flow** | `TCP`    | TCP connection reliable banata hai — har packet ka jawab chahta hai. Agar koi issue ho, woh retry karta hai.                  |
| **Application Support**  | `TCP`    | TCP/UDP ports use karke har app ko ek unique channel deta hai (jaise HTTP = port 80, HTTPS = 443).                            |
| **Name Resolution**      | `DNS`    | Tu naam likhta hai (facebook.com), DNS use karke woh uska IP address dhoondta hai — warna tujhe manually IP likhna parta.     |

---

## 🧠 Real-World Example:

Tu WhatsApp pe message bhejta hai:

1. WhatsApp (Application Layer)
2. Message TCP ke zariye safe banaya jata hai (Transport)
3. IP address lagta hai receiver ka (Internet)
4. Data wifi ya cable se nikalta hai (Link)

Wahan wohi reverse process hota hai.


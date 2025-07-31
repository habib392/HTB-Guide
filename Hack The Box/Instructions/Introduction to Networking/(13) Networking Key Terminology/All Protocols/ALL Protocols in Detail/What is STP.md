
### 📘 **Spanning Tree Protocol**

**📌 Protocol Name:** STP (Spanning Tree Protocol)
**📚 Layer:** Layer 2 (Data Link Layer)
**🎯 Purpose:** Loop ko rokna jab multiple switches connected hoon

---

### 🔍 **STP kya karta hai?**

STP aik aisa protocol hai jo **network loop** banne se bachata hai jab switches zyada ho jaayein ya jab **redundant connections** diye jaayein.
Loop ka matlab hota hai — data ghoomta rahe bina rukay, jiska result hota hai:

* Network slow ya crash ho jata hai
* Broadcast storm aa jata hai
* Devices hang kar jati hain

---

### 💡 **Real-Life Example:**

Maan lo:

* PC1 department 1 mein hai
* PC2 department 5 mein hai
* Dono ke darmiyan 5 switches lage hain
* PC1 data bhejta hai PC2 ko in switches ke zariye

Ab agar switch 3 ya switch 5 kharab ho jaye, toh data ruk jata hai. Isliye network engineers **backup rasta** (yaani second wire) laga dete hain jisse alternate path ban jaata hai.

**Do rastey ban gaye:**

1. **Primary path:**
   PC1 ➡️ S1 ➡️ S2 ➡️ S3 ➡️ S4 ➡️ S5 ➡️ PC2

2. **Backup path:**
   PC1 ➡️ S1 ➡️ S5 ➡️ PC2

Ab dono wires agar same time active hon, toh loop ban sakta hai — matlab data wapas PC1 tak aa sakta hai. Isi ko rokne ke liye **STP** kaam karta hai.

---

### 🛡 **STP ka kaam kya hai?**

* Sirf **ek active path** rakhta hai
* Baaki redundant paths ko **block mode** mein daal deta hai
* Jab active path fail ho jaaye, backup path ko **turant enable** kar deta hai
* Iss se network **kabhi down nahi hota**

---

### 🔁 **Redundancy ka Matlab:**

Redundancy ka matlab hota hai:
**Backup system ya duplicate connection** jo asli system fail hone par kaam aaye.

Real life example:

* Tumhare ghar ka bijli ka UPS – yeh redundancy hai
* Internet mein 2 lines hoon – backup line redundancy hai

---

### 🎯 **Penetration Testing Mein STP ka Use:**

* Attacker STP ko manipulate karke **root bridge** ban sakta hai
* Is se woh network traffic apne paas divert kar sakta hai
* Yeh technique "STP Attack" ya "Bridge Hijacking" kehlati hai

---

### ✅ **STP aaj kal kahan use hota hai?**

**STP aaj bhi use hota hai, especially jab:**

* Network main **zyada switches** hon
* **Redundant links** diye jaayein (backup cables)
* Enterprises ya universities jaise bade setups hoon

**Example:**

* University ka har department ka apna switch hota hai
* Un sab switches ko ek dusre se connect kiya jata hai
* Yahan STP lagaya jata hai taake loop naa banay

---

### 🧠 **Kya STP sirf switches ke sath use hota hai?**

**Haan, STP sirf Layer 2 devices (Switches) ke sath kaam karta hai.**

| Device   | STP Support | Reason                                                                                           |
| -------- | ----------- | ------------------------------------------------------------------------------------------------ |
| ✅ Switch | Yes         | Layer 2 device hai, loops yahin bante hain                                                       |
| ❌ Router | No\*        | Layer 3 device hai, STP nahi chalata, lekin router ke sath connected switches STP use karte hain |
| ❌ Hub    | No          | Dumb device hai, STP samajhta hi nahi                                                            |

\*Router STP ko **forward** kar sakta hai agar usmein **Switching module** ho (e.g. Layer 3 Switch).

---

### 📌 **Toh agar network main sirf router aur hub ho...**

* STP ka koi kaam nahi
* Lekin jaise hi tum **2 ya zyada switches lagao**, aur unko redundant tariqay se connect karo, STP lagana **must** ban jata hai
* Warna **loop** banega, aur network **down** hoga

---

### 🔧 Aaj Kal Ka Use (Modern Use)

Aaj kal switches mein **RSTP (Rapid STP)** ya **MSTP (Multiple STP)** use hota hai — yeh updated versions hain jo fast kaam karte hain.

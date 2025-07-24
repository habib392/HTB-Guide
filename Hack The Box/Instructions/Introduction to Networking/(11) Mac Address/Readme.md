### **MAC Address ki Representation**
MAC address 48-bit ka unique identifier hai jo network devices ke liye hota hai. Yeh 6 octets mein hota hai, har octet 8 bits ka. Inhe binary aur hexadecimal (hex) mein likha jata hai.

#### **Broadcast MAC Address**
- **Binary:** `1111 1111` | `1111 1111` | `1111 1111` | `1111 1111` | `1111 1111` | `1111 1111`
- **Hex:** `FF:FF:FF:FF:FF:FF`
- Yeh broadcast address hai jo LAN ke sab devices tak data bhejta hai.

#### **Global OUI aur Locally Administered**
- Pehle octet ka second last bit batata hai ke MAC address Global OUI hai ya Locally Administered.
  - **Global OUI:** IEEE ke standard ke mutabiq hota hai, second last bit `0` hota hai.
  - **Locally Administered:** User ya admin khud set karta hai, second last bit `1` hota hai.

#### **Global OUI Example**
- **Binary:** `1101 1100` | `1010 1101` | `1011 1110` | `1110 1111` | `0001 0011` | `0011 0111`
- **Hex:** `DC:AD:BE:EF:13:37`
- Pehle octet ka second last bit `0` hai, yani yeh IEEE ka Global OUI hai.

#### **Locally Administered Example**
- **Binary:** `1101 1110` | `1010 1101` | `1011 1110` | `1110 1111` | `0001 0011` | `0011 0111`
- **Hex:** `DE:AD:BE:EF:13:37`
- Pehle octet ka second last bit `1` hai, yani yeh manually set kiya gaya Locally Administered address hai.

---

### **MAC Address aur Security**
- MAC addresses ko badla ya spoof kiya ja sakta hai, isliye inhe security ya identification ke liye akela use nahi karna chahiye.
- Network admins ko aur security measures lagane chahiye:
  - **Network Segmentation:** Network ko chhote hisson mein baantna.
  - **Strong Authentication Protocols:** Devices ko passwords ya certificates se verify karna.

#### **MAC Address se Attacks**
1. **MAC Spoofing:** Device ka MAC address badal kar kisi aur device ka MAC copy karna, taake unauthorized access mil sake.
2. **MAC Flooding:** Bohat saare fake MAC addresses ke sath packets bhejna taake switch ki MAC table bhar jaye aur woh hub ki tarah kaam kare.
3. **MAC Address Filtering Exploitation:** Specific MAC addresses ke liye configured networks mein spoofed MAC address se access haasil karna.

---

### **Address Resolution Protocol (ARP)**
ARP ek network protocol hai jo Layer 3 (IP address) ko Layer 2 (MAC address) ke sath map karta hai. Yeh LAN mein devices ke communication ke liye zaroori hai.

#### **ARP ka Kaam**
- Jab ek device LAN mein doosre device se baat karna chahta hai, to usay destination ka MAC address chahiye.
- Device broadcast message bhejta hai jismein destination IP aur apna MAC address hota hai.
- Matching IP wala device apna MAC address reply mein bhejta hai, aur dono devices MAC addresses ke zariye baat karte hain.
- Yeh process ARP resolution kehlata hai. Yeh efficient hai kyunke MAC addresses ke zariye data bheja jata hai.

#### **ARP Request aur Reply**
- **ARP Request:** Device broadcast message bhejta hai, “Is IP ka MAC address kya hai?” (e.g., “Who has 10.129.12.101? Tell 10.129.12.100”).
- **ARP Reply:** Matching IP wala device jawab deta hai, “Mera MAC address yeh hai” (e.g., “10.129.12.101 is at AA:AA:AA:AA:AA:AA”).

#### **Tshark Capture of ARP**
1. `10.129.12.100 -> 10.129.12.255 ARP 60 Who has 10.129.12.101? Tell 10.129.12.100`
2. `10.129.12.101 -> 10.129.12.100 ARP 60 10.129.12.101 is at AA:AA:AA:AA:AA:AA`
3. `10.129.12.102 -> 10.129.12.255 ARP 60 Who has 10.129.12.103? Tell 10.129.12.102`
4. `10.129.12.103 -> 10.129.12.102 ARP 60 10.129.12.103 is at BB:BB:BB:BB:BB:BB`
- Pehli aur teesri lines mein device IP ka MAC address poochta hai. Doosri aur chauthi lines mein destination device apna MAC address bhejta hai.

---

### **ARP Spoofing**
ARP protocol mein authentication nahi hoti, isliye yeh attacks ke liye vulnerable hai. Ek attack hai **ARP Spoofing** (ya ARP Cache Poisoning).

#### **ARP Spoofing Kya Hai?**
- Hacker fake ARP replies bhejta hai taake apna MAC address kisi legitimate device ke IP ke sath associate kare.
- Is se traffic jo kisi aur device ke liye tha, hacker ke paas jata hai. Yeh Man-in-the-Middle (MITM) attack ka tareeka hai.
- Tools jaise Ettercap ya Cain & Abel use hote hain.

#### **Tshark Capture mein ARP Spoofing**
1. `10.129.12.100 -> 10.129.12.101 ARP 60 10.129.12.101 is at AA:AA:AA:AA:AA:AA`
2. `10.129.12.100 -> 10.129.12.255 ARP 60 Who has 10.129.12.101? Tell 10.129.12.100`
3. `10.129.12.101 -> 10.129.12.100 ARP 60 10.129.12.101 is at BB:BB:BB:BB:BB:BB`
4. `10.129.12.100 -> 10.129.12.101 ARP 60 10.129.12.101 is at AA:AA:AA:AA:AA:AA`
- Pehli aur chauthi lines mein hacker fake ARP message bhejta hai ke 10.129.12.101 ka MAC address AA:AA:AA:AA:AA:AA hai.
- Doosri aur teesri lines mein target device request aur reply deta hai, lekin hacker ke fake messages se ARP cache poison ho jata hai, aur traffic hacker ke paas jata hai.

#### **ARP Spoofing ke Istemaal**
- Sensitive information churana, jaise passwords.
- Traffic redirect karna.
- MITM attacks karna.

#### **Bachao ke Tareeke**
- Secure protocols jaise IPSec ya SSL use karna.
- Firewalls aur Intrusion Detection Systems (IDS) lagana.
- Dynamic ARP Inspection (DAI) ya static ARP entries use karna.

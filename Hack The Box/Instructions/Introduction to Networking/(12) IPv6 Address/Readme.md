# IPv6 Notes

## **IPv6 Kya Hai?**
IPv6, IPv4 ka upgraded version hai jo 128-bit addresses deta hai, jabke IPv4 32-bit ka hai. Yeh internet ke devices ke liye unique addresses provide karta hai, kyunki IPv4 ke 4.3 billion addresses ab kaafi nahi hain.

**Real-Life Example:**
- Tera ghar ka WiFi router IPv6 use karta hai. Jab tu phone connect karta hai, to usay ek IPv6 address milta hai, jaise `fe80:bac9:b5ff:fecc:a623`, aur ek IPv4 address, jaise `192.168.1.100`. Yeh dual stack mode hai, jismein dono addresses sath kaam karte hain.

**Kyun IPv6?**
- IPv4 ke addresses khatam ho rahe hain kyunki devices (phones, TVs, smart bulbs) bohat zyada ho gaye hain. IPv6 340 undecillion addresses deta hai, jo saalon tak khatam nahi honge.
- Har device ko unique public address milta hai, to NAT (Network Address Translation) ki zarurat nahi.

## **IPv6 Address Structure**
IPv6 address 128-bit ka hota hai, jo 8 blocks mein divide hota hai. Har block 16-bit ka hai aur hexadecimal (hex) mein likha jata hai, blocks ko colon (`:`) se separate kiya jata hai.

**Example:**
- **Full Form:** `fe80:0000:0000:0000:dd80:b1a9:6687:2d3b/64`
- **Short Form:** `fe80::dd80:b1a9:6687:2d3b/64`

**Parts:**
- **Network Prefix:** Pehle 64-bit (jaise `fe80::/64`) network ya subnet ko identify karte hain.
- **Interface Identifier:** Baki 64-bit (jaise `dd80:b1a9:6687:2d3b`) device ko identify karte hain, jo MAC address se banaya jata hai.

**Real-Life Example:**
- Tera phone ka MAC address `b8:c9:b5:cc:a6:23` hai. IPv6 isay 64-bit interface identifier mein convert karta hai: `bac9:b5ff:fecc:a623`. Router ka prefix `fe80::/64` add hone se pura address banta hai: `fe80:bac9:b5ff:fecc:a623/64`.

**Prefix Lengths:**
- Default prefix `/64` hota hai, lekin ISPs `/56` ya `/48` bhi dete hain, jo zyada subnets allow karte hain.
- **Example:** Agar tera ISP `/56` deta hai, to tu ghar mein alag subnets bana sakta hai, jaise ek guest WiFi ke liye, ek IoT devices ke liye.

## **IPv6 Notation Rules (RFC 5952)**
IPv6 addresses ko short aur readable banane ke rules:
1. Sab alphabets lowercase mein (jaise `a`, na ke `A`).
2. Har block ke shuru ke zeros hatao (jaise `0001` se `1`).
3. Consecutive zero blocks ko `::` se replace karo, sirf ek baar, left se shuru karte hue.

**Example:**
- Full: `2001:0db8:0000:0000:0000:0000:1234:5678`
- Short: `2001:db8::1234:5678`

**Real-Life Example:**
- Tera router ka IPv6 address `2001:0db8:0000:0000:0000:0000:0000:0001` hai. Short form mein yeh `2001:db8::1` ban jata hai, jo admin panel mein readable hai.

## **IPv6 Address Types**
IPv6 mein teen types ke addresses hote hain:

1. **Unicast:**
   - Ek single device ke liye.
   - **Example:** Tu apne phone se friend ko WhatsApp message bhejta hai using `2001:db8::1`. Yeh sirf uske phone (`2001:db8::2`) tak jata hai.

2. **Anycast:**
   - Multiple devices ke liye ek address, lekin packet sirf qareebi device tak jata hai.
   - **Example:** Tu Google.com kholta hai. Google ka anycast address `2001:4860:4860::8888` qareebi server (jaise Dubai) tak request bhejta hai, taake speed fast ho.

3. **Multicast:**
   - Multiple devices ko same packet bhejta hai.
   - **Example:** Tu ghar ke smart devices (TV, bulb) ko multicast address `ff02::1` par command bhejta hai, jaise “sab lights band karo”. Sab devices ek sath respond karte hain.

**Note:** IPv6 mein broadcast nahi hota, uski jagah multicast use hota hai jo zyada efficient hai.

## **IPv6 vs IPv4**
| **Feature**            | **IPv4**                              | **IPv6**                              |
|------------------------|---------------------------------------|---------------------------------------|
| **Bit Length**         | 32-bit (4 octets)                    | 128-bit (8 blocks)                   |
| **Addressing Range**   | ~4.3 billion                         | ~340 undecillion                     |
| **Representation**     | Decimal (e.g., `192.168.1.100`)      | Hexadecimal (e.g., `fe80::1`)        |
| **Prefix Notation**    | `10.10.10.0/24`                     | `fe80::/64`                          |
| **Dynamic Addressing** | DHCP                                 | SLAAC / DHCPv6                       |
| **IPsec**              | Optional                             | Mandatory                            |

**Real-Life Example:**
- Tera ghar ka router IPv4 mein ek public IP (`203.135.x.x`) use karta hai aur NAT se sab devices ko private IPs (`192.168.1.x`) deta hai. IPv6 mein har device ko unique global address milta hai, jaise `2001:db8::1`, bina NAT ke.

## **IPv6 ke Advantages**
1. **Larger Address Space:**
   - **Example:** Tera ghar mein 20 devices (phone, TV, smart bulb) hain. IPv6 har device ko unique address deta hai, to setup asaan hota hai, jabke IPv4 mein NAT ke wajah se complexity hoti hai.

2. **SLAAC (Stateless Address Autoconfiguration):**
   - Devices khud apna IPv6 address bana lete hain using router ka prefix aur MAC address.
   - **Example:** Tu naya smart TV WiFi se connect karta hai. Router ka prefix `2001:db8::/64` hai, to TV apna address `2001:db8::21a:2bff:fe3c:4d5e` khud banata hai, bina manual setup ke.

3. **Multiple Addresses per Interface:**
   - Ek device ke do ya zyada IPv6 addresses ho sakte hain (link-local aur global).
   - **Example:** Tera phone link-local address `fe80:bac9:b5ff:fecc:a623` use karta hai ghar ke printer se baat karne ke liye, aur global address `2001:db8::1` Netflix se connect karne ke liye.

4. **Faster Routing:**
   - Simple headers ke wajah se routing fast hota hai.
   - **Example:** Tu PUBG khelta hai. IPv6 ke direct connection se ping kam hota hai (20ms), jabke IPv4 mein NAT ke wajah se 50-60ms ho sakta hai.

5. **IPsec (End-to-End Encryption):**
   - Data encryption mandatory hai.
   - **Example:** Tu HBL app se banking karta hai. IPv6 ka IPsec tera username aur password encrypt karta hai, to hacker intercept nahi kar sakta.

6. **Large Data Packets (4 GByte):**
   - **Example:** Tu 4K movie Netflix par stream karta hai. IPv6 ke bade packet size ke wajah se movie bina buffering ke chalti hai.

## **Dual Stack**
Router aur devices IPv4 aur IPv6 dono support karte hain taake transition smooth ho.

**Example:**
- Tu Google (IPv6) aur local news site (IPv4) dono kholta hai. Tera phone IPv6 (`fe80:bac9:b5ff:fecc:a623`) aur IPv4 (`192.168.1.100`) addresses use karta hai automatically, tujhe pata bhi nahi chalta.

## **Hexadecimal System**
Hexadecimal (hex) ek number system hai jo 16 states (0-9 aur a-f) ko represent karta hai, taake binary readable ho. Yeh IPv6 addresses ke liye use hota hai kyunki 128-bit ko decimal mein likhna lamba hota hai.

**Table:**
| **Decimal** | **Hex** | **Binary** |
|-------------|---------|------------|
| 1           | 1       | 0001       |
| 2           | 2       | 0010       |
| 10          | a       | 1010       |
| 15          | f       | 1111       |

**Example (IPv4 to Hex):**
- Tera IPv4 address `192.168.1.100`:
  - **Binary:** `11000000.10101000.00000001.01100100`
  - **Hex:** `c0:a8:01:64`
  - **Decimal:** `192.168.1.100`

**IPv6 Example:**
- Tera phone ka IPv6 address `fe80:bac9:b5ff:fecc:a623`. Yahan `f` = 15, `e` = 14, `c` = 12. Hex binary se chhota aur readable hai.

## **Kaise Check Karo?**
- **Linux/Phone Command:**
  ```bash
  ip -6 addr
  ```
  - Yeh tera IPv6 address dikhaye ga, jaise `fe80:bac9:b5ff:fecc:a623`.

- **Router Admin Panel:** Log in karke dekho ke IPv6 enabled hai aur kaunsa prefix mila hai (jaise `/64` ya `/56`).

**Real-Life Example:**
- Tera phone WiFi par hai. Yeh link-local IPv6 (`fe80:bac9:b5ff:fecc:a623`) use karta hai ghar ke printer se baat karne ke liye, aur global IPv6 (`2001:db8::1`) Netflix ke liye. Tera IPv4 (`192.168.1.100`) purani websites ke liye kaam karta hai.



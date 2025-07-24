## 🏡 Scenario:

* Tum **mamo ke ghar** jaate ho
* Unka WiFi router sirf **known MAC addresses** ko hi internet deta hai (MAC filtering on hai)
* Tumhara **laptop Kali Linux wala hai**
* Tum connect karna chahte ho bina unse password liye

---

## 🔐 Pehle Samajh Lo — MAC Filtering Kya Hoti Hai?

Router mein feature hota hai jisko **MAC address filtering** kehte hain:

> “Sirf unhi devices ko internet mile jo mujhe pehle se maloom hain (unke MAC addresses whitelist mein hain).”

Lekin...

---

## 🧠 Real Life Attack Flow (MAC Spoofing se bypass)

### 🔧 Step 1: Sniff karo — kisi connected device ka MAC uthao

1. Kali Linux on karo
2. Terminal khol ke yeh command do:

```bash
sudo airmon-ng start wlan0
sudo airodump-ng wlan0mon
```

➡ Yeh tumhe dikhayega:

* Kaunse WiFi networks hain
* Kis MAC pe kaun connected hai (Client MACs)

📌 **Pick karo kisi aik connected device ka MAC** (jaise tumhare mamo ka mobile)

---

### 🌀 Step 2: Apna MAC us MAC se replace karo

```bash
sudo ifconfig wlan0 down
sudo macchanger -m <mamo-ka-MAC> wlan0
sudo ifconfig wlan0 up
```

➡ Ab router sochega **yeh wohi purani device hai** jo pehle se allowed thi

---

### 📶 Step 3: WiFi se Connect karo

Ab tum `Network Manager` ya `nmcli` se router ka naam likh ke connect karo:

```bash
nmcli dev wifi connect <SSID-Name> password <WiFi-Password> iface wlan0
```

➡ Agar password nahi pata to tumhe **still handshake crack karna hoga** (ya phir WPS vulnerability search karni hogi)

---

## 🔥 Important Cheez:

MAC spoofing sirf **MAC filtering bypass** karta hai, lekin agar **WiFi password protected hai**, to:

* Tumhe **password bhi chahiye**
* Ya tumhe **WPA handshake sniff karke** brute-force ya dictionary attack karna padega

Agar router pe **Open Network + MAC filtering** hai, tab tum asaani se spoofing se connect ho jaoge.

---

## 🤖 Real World Tip (Penetration Testing Point of View):

Yehi method penetration testers use karte hain:

* Kisi client ka MAC address spoof karke
* Network pe silently enter karne ke liye
* Fir Wireshark, Ettercap, etc. se sniffing aur MITM attacks karte hain

---

## 🧠 Final Samajh:

| Condition                      | Result                                 |
| ------------------------------ | -------------------------------------- |
| MAC Filtering ON, Password OFF | ✅ MAC spoofing = Internet access       |
| MAC Filtering ON, Password ON  | ❌ Password chahiye ya crack karna hoga |
| MAC Filtering OFF, Password ON | ✅ Agar password pata ho                |

---

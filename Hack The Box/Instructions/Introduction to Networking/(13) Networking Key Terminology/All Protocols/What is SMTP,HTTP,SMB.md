- SMTP, HTTP, aur SMB Notes

## **SMTP (Simple Mail Transfer Protocol)**

### **Kya Hai?**

- SMTP ek system hai jo email bhejne ke liye use hota hai. Yeh ek postman jaisa kaam karta hai jo email ko ek jagah se doosri jagah (server se server) pohanchata hai.
- Yeh sirf email bhejne ke liye hai; lene ke liye POP3 ya IMAP use hote hain.

### **Kahan Use Hota Hai?**

- Har email service mein, jaise Gmail, Outlook, Yahoo, ya company ke custom emails (info@company.com).
- Websites ya apps jo automatic emails bhejte hain, jaise order confirmations ya password resets.

### **Main Purpose**

- Email ko ek server se doosre server ya client se server tak bhejna.

### **Uses**

- **Personal Emails**: Dost ko Gmail se email bhejna.
- **Automated Emails**: Online shopping ke baad “order confirmed” email.
- **Marketing**: Companies ke sale offer emails.
- **Notifications**: Bank se “transaction alert” email.

### **Penetration Testing ke Liye**

- **Problems**:
  - Agar SMTP server thik se set nahi, to hackers fake (phishing) emails bhej sakte hain, jaise “tum ne reward jeeta” wali fake emails.
  - Weak passwords ya no encryption se hackers spam emails bhej sakte hain.
- **Kya Seekhein**:
  - SMTP server ke secure settings check karna (jaise TLS encryption).
  - Tools jaise **Nmap** ya **Metasploit** se vulnerabilities scan karna.
  - SPF, DKIM, DMARC settings samajhna taake fake emails roke ja sakein.

### **Kya Aaj Kal Chalta Hai?**

- Haan, SMTP aaj bhi email systems ka core hai, secure (TLS/SSL) ke saath.
- Insecure SMTP configurations ab kam use hoti hain.

### **Real-Life Examples**

- **Gmail**: Tu Gmail se dost ko email bhejta hai, SMTP usko dost ke server (jaise Yahoo) tak pohanchata hai.
- **Shopping**: Amazon se order ke baad “order confirmation” email SMTP se aata hai.
- **Job Application**: Company ko job email bhejta hai, SMTP usko company server tak le jata hai.

- SMTP har email platform (Gmail, Outlook, Yahoo) mein email bhejne ke liye use hota hai.
- Secure hai jab sahi implement ho, warna hackers phishing emails bhej sakte hain.

---

## **HTTP (Hypertext Transfer Protocol)**

### **Kya Hai?**

- HTTP ek system hai jo internet pe web pages ya data bhejne aur lene ke liye use hota hai. HTTPS iska secure version hai jo encryption ke saath kaam karta hai.

### **Kahan Use Hota Hai?**

- Zyadatar websites ke liye, jab browser (Chrome, Firefox) server se web pages lata hai.
- Apps mein jo server se data lete hain, jaise weather apps ya APIs.

### **Main Purpose**

- Web pages (HTML, CSS, JS, images) ya data ko browser ya app tak pohanchana.
- Client (browser/app) aur server ke beech communication.

### **Uses**

- **Web Browsing**: Websites jaise Google, YouTube load karna.
- **APIs**: Apps ke liye data exchange, jaise Twitter se tweets lena.
- **File Downloads**: Browser se PDFs ya images download karna.
- **Web Forms**: Login ya search queries server tak bhejna.
- **Streaming**: Netflix jaisa video streaming.

### **Penetration Testing ke Liye**

- **Problems**:
  - HTTP (non-secure) mein data unencrypted hota hai, hackers man-in-the-middle attacks kar sakte hain.
  - Weak HTTPS certificates ya outdated encryption exploitable hain.
  - XSS (malicious scripts) ya SQL Injection (database attacks) web pages pe possible hain.
- **Kya Seekhein**:
  - HTTPS ke valid SSL certificates check karna.
  - Tools jaise **Burp Suite** ya **OWASP ZAP** se web vulnerabilities test karna.
  - XSS, SQL Injection, CSRF jaise attacks samajhna.
  - HTTP headers (jaise Content-Security-Policy) ka audit.

### **Kya Aaj Kal Chalta Hai?**

- Haan, HTTPS ab standard hai kyunki secure hai. HTTP purana aur insecure hai, sirf local testing mein use hota hai.

### **Real-Life Examples**

- **Google Search**: Google.com pe search karna, HTTPS query aur results transfer karta hai.
- **Online Shopping**: Amazon pe product page kholta hai, HTTPS images aur prices lata hai.
- **API Calls**: Weather app tera location HTTPS se server tak bhejta hai aur data lata hai.

---

## **SMB (Server Message Block)**

### **Kya Hai?**

- SMB ek system hai jo network mein computers ke beech files, folders, ya printers share karne ke liye use hota hai. Yeh ek magic box jaisa hai jo shared cheezein sab devices ko deta hai.
- Zyadatar Windows systems mein common hai.

### **Network Kya Hai?**

- Network tab hota hai jab do ya zyada devices (phones, laptops, printers) ek router ya Wi-Fi se connect hote hain taake ek doosre se baat kar sakein.
- Example: Ghar ka Wi-Fi jismein tera phone, laptop, aur printer connected hain.

### **Kahan Use Hota Hai?**

- Windows networks mein, jaise offices, schools, ya ghar mein.
- Jahan files ya printers share karne hon.

### **Main Purpose**

- Network mein files (documents, photos) ya printers share karna taake sab devices use kar sakein.

### **Uses**

- **File Sharing**: Network pe shared folder se documents access karna.
- **Printer Sharing**: Ek printer ko network ke sab devices se use karna.
- **Backups**: Important files ko network drive pe save karna.
- **Teamwork**: Project ke liye shared folder mein team kaam karta hai.

- Tera phone aur bhai ka phone ek router se connected hain, yani ek network pe. Files transfer (jaise photos) SMB se ho sakta hai, especially Windows devices pe.
- Tera phone aur printer ek network pe hain, to tu phone se print kar sakta hai kyunki SMB printer ko share karta hai.

### **Penetration Testing ke Liye**

- **Problems**:
  - Purana SMB (SMBv1) insecure hai, hackers isse files chura sakte hain ya virus daal sakte hain (jaise WannaCry).
  - Weak permissions ya passwords se hackers shared folders access kar sakte hain.
- **Kya Seekhein**:
  - SMBv1 band hai ya nahi, check karna.
  - Tools jaise **Metasploit** ya **Nmap** se SMB vulnerabilities scan karna.
  - Shared folders ke permissions check karna taake sirf sahi log access karein.

### **Kya Aaj Kal Chalta Hai?**

- Haan, SMB ab bhi Windows networks mein use hota hai, lekin secure versions (SMBv2, SMBv3).
- SMBv1 ab outdated aur hackable hai, isliye avoid hota hai.

### **Real-Life Examples**

- **Office**: Company mein shared folder jahan employees reports save karte hain, SMB se access hota hai.
- **Home**: Ghar mein printer jo phone aur laptop dono se print karta hai, SMB ke zariye share hota hai.
- **School**: Computer lab mein shared folder jahan students assignments save karte hain, SMB se kaam karta hai.

---

## **Quick Comparison**

- **SMTP**: Email bhejne ka postman, har email service mein.
- **HTTP/HTTPS**: Web pages ya data internet pe transfer karne ka system, websites aur apps mein.
- **SMB**: Network mein files/printers share karne ka magic box, Windows systems mein.

## **Cyber Security Relevance**

- **SMTP**: Phishing emails (fake “reward” emails) se bachne ke liye secure settings (SPF, DKIM) seekhna.
- **HTTP/HTTPS**: Web attacks (XSS, SQL Injection) ke liye Burp Suite ya OWASP ZAP se testing seekhna.
- **SMB**: Weak permissions ya purane SMBv1 se bachne ke liye Nmap/Metasploit se scan karna seekhna.


# 🛡️ SteganoChat

<p align="center">
  <img src="https://capsule-render.vercel.app/render?type=waving&color=auto&height=200&section=header&text=SteganoChat&fontSize=90" />
</p>

<p align="center">
  <img src="https://img.shields.io/github/license/CagatayTurunc/SteganoChat?style=for-the-badge" />
  <img src="https://img.shields.io/github/stars/CagatayTurunc/SteganoChat?style=for-the-badge" />
  <img src="https://img.shields.io/github/issues/CagatayTurunc/SteganoChat?style=for-the-badge" />
  <img src="https://img.shields.io/github/languages/top/CagatayTurunc/SteganoChat?style=for-the-badge" />
</p>

---

## 📖 Hakkında

**SteganoChat**, gizlilik ve güvenliği artırmak amacıyla geliştirilmiş,  
mesajları **dijital görseller içerisine gizleyerek** ileten istemci–sunucu tabanlı bir sohbet uygulamasıdır.

Uygulama, klasik metin tabanlı mesajlaşmanın aksine **steganografi + kriptografi** yaklaşımlarını birlikte kullanır.

> “Sadece şifrelemek değil, mesajın varlığını da gizlemek.”

---

## ✨ Temel Özellikler

- 🔒 **LSB Steganografi:** Kullanıcı parolaları PNG görsellerin piksellerine gömülür  
- 🔐 **DES Şifreleme:** Mesajlar sunucu üzerinden güvenli biçimde iletilir  
- 👥 **Çoklu İstemci Desteği:** Thread tabanlı socket mimarisi  
- 📡 **Gerçek Zamanlı Sohbet:** Anlık mesaj iletimi  
- 📥 **Çevrimdışı Mesaj Desteği:** Kullanıcı offline iken mesajlar sunucuda tutulur  
- 🖥️ **Swing Arayüz:** Java Swing ile geliştirilmiş masaüstü istemci  

---

## 🛠️ Kullanılan Teknolojiler

- **Programlama Dili:** Java  
- **Ağ İletişimi:** Java Socket Programming  
- **Eşzamanlılık:** Multi-threading  
- **Steganografi:** LSB (Least Significant Bit)  
- **Kriptografi:** DES (ECB, PKCS5Padding)  
- **Arayüz:** Java Swing  
- **Çalışma Ortamı:** Linux (Kali Linux önerilir)  

---

## 🔄 Sistem Çalışma Mantığı

1. **Kayıt:**  
   Kullanıcı, gizli anahtarını seçtiği bir PNG görsele gömer ve sunucuya gönderir.

2. **Anahtar Çıkarma:**  
   Sunucu, görselden anahtarı çıkarır ve RAM üzerinde güvenli şekilde saklar.

3. **Mesajlaşma:**  
   - Gönderen mesajı kendi anahtarıyla şifreler  
   - Sunucu mesajı çözer ve alıcının anahtarıyla tekrar şifreleyerek iletir  

4. **Çevrimdışı Destek:**  
   Alıcı offline ise mesajlar `Map` yapısında saklanır, online olduğunda teslim edilir.

---

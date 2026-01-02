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

**SteganoChat**, gizlilik ve güvenliği en üst düzeye çıkarmak için tasarlanmış yenilikçi bir sohbet uygulamasıdır. Standart mesajlaşma yöntemlerinin ötesine geçerek, mesajlarınızı steganografi tekniklerini kullanarak dijital görsellerin içerisine gizler.

> "Görünmeyeni korumak, sadece şifrelemekten daha güçlüdür."

## 🛠️ Teknik Özellikler

| Özellik | Açıklama | Teknoloji / Yöntem |
| :--- | :--- | :--- |
| **Kimlik Doğrulama** | Parolanın resim piksellerine gizlenmesi | **LSB (Least Significant Bit)** |
| **Mesaj Şifreleme** | Uçtan sunucuya veri gizliliği | **DES (ECB Modu, PKCS5Padding)** |
| **Sunucu Mimarisi** | Çoklu istemci yönetimi | **Multi-threading & Socket Programming** |
| **Mesajlaşma Tipi** | Çevrimiçi ve Çevrimdışı iletim | **Store-and-Forward (Depola-İlet)** |
| **Arayüz** | Modern ve dinamik kullanıcı deneyimi | **Java Swing (Glassmorphism UI)** |

---

## 🔄 Çalışma Mantığı (System Flow)

1.  **Kayıt (Register):** Kullanıcı `secretKey` değerini seçtiği bir PNG resmine gömer ve sunucuya iletir.
2.  **Anahtar Çıkarma (Key Extraction):** Sunucu resmi işleyerek içindeki anahtarı çıkarır ve güvenli belleğe (RAM) kaydeder.
3.  **Güvenli Sohbet (Secure Chat):**
    * İstemci, mesajı kendi anahtarıyla **DES** kullanarak şifreler.
    * Sunucu mesajı alır, gönderenin anahtarıyla çözer ve alıcının anahtarıyla tekrar şifreleyerek iletir.
4.  **Çevrimdışı Destek (Offline Support):** Alıcı çevrimdışı ise mesaj sunucuda (`Map` yapısında) bekletilir, online olduğu anda teslim edilir.

---

## 🚀 Kurulum
> [!IMPORTANT]
> Projenin **Linux (Kali)** ortamında çalıştırılması teknik uyumluluk açısından gereklidir. 

Projeyi yerel makinenizde çalıştırmak için aşağıdaki adımları izleyin:


### 1. Adım: Derleme
Terminali açın ve proje dizininde şu komutu çalıştırın:
```bash
javac *.java
2. Adım: Sunucuyu Ayağa KaldırmaBashjava MainServer
3. Adım: İstemciyi BaşlatmaBashjava RegisterForm
📂 Kayıtlar ve Log SistemiSistem, analiz ve savunma süreçleri için detaylı log dosyaları üretir:📄 server_logs.txt: Mesajların şifrelenme/çözülme ve iletim süreçlerini anlık kaydeder.📄 stego_debug.txt: Resim piksellerindeki bit değişimlerini detaylıca raporlar.📄 registered_users.txt: Kayıtlı kullanıcıların kalıcı listesini tutar.✅ Ödev Uyumluluk Tablosu#İstenen KoşulDurumTeknik Karşılık1Birden fazla Client desteği✅Thread tabanlı ClientHandler yapısı2LSB ile parola saklama✅SteganoManager.encode algoritması3Sunucu: Görselden parola çıkarma✅SteganoManager.decode fonksiyonu4Aktif client listesini gösterme✅Dinamik USER_LIST broadcast mesajları5Çevrimdışı mesaj iletilebilmesi✅offlineMessages Map veri yapısı6DES kullanarak şifreleme✅CryptoHelper sınıfı ve 8-byte key sabitleme7Linux üzerinde çalışma şartı✅Kali Linux uyumlu terminal yönetimi

## 📸 Ekran Görüntüleri

| Giriş Ekranı | Sohbet Arayüzü | Görüntü İşleme |
| :---: | :---: | :---: |
| <img src="https://via.placeholder.com/200" width="200"> | <img src="https://via.placeholder.com/200" width="200"> | <img src="https://via.placeholder.com/200" width="200"> |

*(Lütfen gerçek ekran görüntülerini buraya ekle)*

## 🤝 Katkıda Bulunma

Katkı sağlamak isterseniz lütfen şu adımları izleyin:
1. Projeyi çatallayın (Fork).
2. Yeni bir özellik dalı (Branch) oluşturun (`git checkout -b feature/YeniOzellik`).
3. Değişikliklerinizi kaydedin (`git commit -m 'Yeni özellik eklendi'`).
4. Dalınızı gönderin (`git push origin feature/YeniOzellik`).
5. Bir Çekme İsteği (Pull Request) açın.

## 📄 Lisans

Bu proje **MIT Lisansı** altında lisanslanmıştır. Daha fazla bilgi için `LICENSE` dosyasına göz atın.

---

<p align="center"> <b>Geliştiren: <a href="https://www.google.com/search?q=https://github.com/CagatayTurunc">Çağatay Turunç</a></b>


<i>Bilgisayar Mühendisliği Öğrencisi</i> </p>
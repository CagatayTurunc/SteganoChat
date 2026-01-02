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





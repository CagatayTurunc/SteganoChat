SteganoChat: Secure Messaging Protocol with LSB & DES
Bu proje, Java programlama dili ve ağ soket programlama teknikleri kullanılarak geliştirilmiş, steganografi ve kriptografi yöntemlerini birleştiren güvenli bir anlık mesajlaşma sistemidir. Sistem, klasik parola doğrulama yöntemleri yerine, parolanın bir görüntü içerisine gizlendiği özgün bir kimlik doğrulama mekanizması sunar.

🚀 Öne Çıkan Özellikler
Çoklu İstemci Desteği: Multi-threading yapısı sayesinde aynı anda birçok kullanıcı sisteme bağlanabilir ve mesajlaşabilir.

Gelişmiş Steganografi (LSB): Kullanıcı parolaları, PNG formatındaki resimlerin piksellerine Random Seed kullanılarak dağıtılır; bu sayede görselde desen bozulması önlenir.

Uçtan Sunucuya Şifreleme (DES): Mesajlar, istemci tarafında DES algoritması (ECB Modu, PKCS5Padding) ile şifrelenerek sunucuya iletilir.

Offline Mesaj Desteği: Alıcı çevrimdışı (offline) olsa dahi mesajlar sunucuda güvenli bir kuyrukta saklanır ve alıcı çevrimiçi olduğu anda iletilir.

Modern Arayüz: Java Swing kullanılarak hazırlanan "Glassmorphism" etkili, kullanıcı dostu kayıt ve sohbet ekranları.

🛠 Teknik Mimari
Proje, tam bir güvenli mesajlaşma döngüsü sağlar:

Kayıt (Registration): İstemci, parolasını (Secret Key) seçilen bir PNG dosyasının son bitlerine (LSB) gömer ve bu "stego-resmi" sunucuya gönderir.

Anahtar Çıkarma: Sunucu, gelen resimden gizli anahtarı ayrıştırır ve bu anahtarı kullanıcının oturumu boyunca güvenli bir ConcurrentHashMap yapısında tutar.

Güvenli İletişim: * İstemci: Mesajı kendi anahtarıyla şifreler.

Sunucu: Gelen şifreli mesajı gönderenin anahtarıyla çözer, alıcının anahtarıyla tekrar şifreleyerek iletir.

Alıcı: Sunucudan gelen veriyi kendi gizli anahtarıyla çözerek görüntüler.

💻 Kurulum ve Çalıştırma
Projenin tam puan alabilmesi için Linux (Kali Linux) ortamında çalıştırılması önerilir.

Derleme
Terminalde proje klasörüne giderek şu komutu çalıştırın:

Bash

javac *.java
Çalıştırma
Sunucuyu Başlatın:

Bash

java MainServer
İstemciyi Başlatın:

Bash

java RegisterForm
📂 Dosya Yapısı
MainServer.java: Bağlantıları kabul eden ve kullanıcı listesini yöneten ana sunucu.

ClientHandler.java: Her bir kullanıcı için özel protokol işlemlerini (şifre çözme/yönlendirme) yöneten sınıf.

SteganoManager.java: LSB algoritması ile veri gömme ve çıkarma işlemlerini yapan motor.

CryptoHelper.java: DES şifreleme ve deşifreleme yardımcı sınıfı.

RegisterForm.java & ChatScreen.java: Swing tabanlı kullanıcı arayüzleri..
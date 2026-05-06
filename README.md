# ORINIUM-KULUBU-IHA-Elektronik-Sistem-Mimarisi ve ÖZGÜN REGÜLATÖR KARTI
Orinium Robotik İHA Elektronik ekip lideri olarak tasarladığım; Pixhawk Cube Orange+ ve Raspberry Pi 5 tabanlı tam kapsamlı elektronik sistem mimarisi. Uzun menzilli telemetri (RFD900x), yedekli haberleşme hatları ve otonom görev yönetimi içeren; güç dağıtımı ve sinyal entegrasyonu tarafımdan projelendirilmiş yüksek performanslı İHA altyapısı.
İHA Elektronik Sistem Mimarisi ve Entegrasyonu

Bu proje, Yıldız Teknik Üniversitesi bünyesinde kurulan **Orinium Robotik Kulübü**'nün geliştirdiği İnsansız Hava Aracı'nın (İHA) tüm elektronik sistem mimarisini içermektedir. Projede **Elektrik-Elektronik Ekip Lideri** olarak; sistemin kablaj planını, güç dağıtımını ve birimler arası haberleşme protokollerini tasarladım.

Sistem Mimarisi ve Teknik Detaylar

Tasarladığım mimari, otonom uçuş kabiliyeti ve yüksek veri iletim hızı odaklıdır:

*   **Uçuş Kontrol Ünitesi (FCU):** **Pixhawk Cube Orange+** kullanılarak ana uçuş kontrolü ve stabilizasyon sağlanmıştır.
*   **Yüksek Performanslı Companion Computer:** **Raspberry Pi 5** entegrasyonu ile otonom görevler, görüntü işleme ve karmaşık algoritma hesaplamaları uçuş sırasında eş zamanlı olarak yürütülmektedir.
*   **Haberleşme Katmanı:** 
    *   **RFD900x Telemetri:** Uzun menzilli veri aktarımı ve yer kontrol istasyonu bağlantısı.
    *   **R9DS Alıcı:** Yedekli kumanda bağlantısı.
    *   **Here4 GPS:** CAN Bus üzerinden yüksek hassasiyetli konumlandırma.
*   **Güç Dağıtım Sistemi:** 
    *   **3S LiPo 3000mAh** batarya beslemesi.
    *   **90A Sigorta ve Acil Durum Butonu:** Sistem güvenliği ve yüksek akım koruması.
    *   Güç modülü üzerinden Raspberry Pi ve Pixhawk için optimize edilmiş voltaj regülasyonu.
*   **Aktüatör ve Kontrol:** 
    *   6 adet servo (Aileron, Elevator, Rudder ve Görev Servoları).
    *   Çift motor ve ESC konfigürasyonu ile itki sistemi yönetimi.

Sistem Blok Diyagramı

Aşağıda, tasarımını yaptığım sistemin birimler arası bağlantılarını ve sinyal yollarını gösteren teknik mimari şeması yer almaktadır:

<img width="2560" height="2082" alt="WhatsApp Image 2026-03-12 at 12 04 42" src="https://github.com/user-attachments/assets/b5657bd9-3bc1-4e74-b5df-5084b647829a" />


> **Mühendislik Notu:** Tasarımda veri trafiğini optimize etmek için kritik sensörler (GPS vb.) CAN hattı üzerinden bağlanmış, telemetri verileri için UART protokolü tercih edilmiştir. Güç hatları, sinyal hatlarından izole edilerek elektromanyetik girişim (EMI) minimuma indirilmiştir.
 Özgün Güç Dağıtım ve Regülatör Tasarımı

İHA üzerindeki farklı voltaj gereksinimlerini (5V, 6V vb.) karşılamak amacıyla tarafımdan tasarlanan yüksek verimli güç modülüdür. 3S LiPo bataryadan gelen ana gücü, sistem bileşenlerinin ihtiyaç duyduğu stabil voltaj seviyelerine dönüştürür.

### Teknik Analiz ve Tasarım Detayları:
*   **Topoloji:** İki adet bağımsız **LM2595-ADJ** tabanlı Buck (Step-Down) Konvertör devresi.
*   **Ayarlanabilir Çıkış:** Potansiyometreler (RV1, RV2) aracılığıyla farklı donanımlar için hassas voltaj ayarı imkanı.
*   **Verimlilik ve Isı Yönetimi:** Anahtarlamalı regülatör kullanımı sayesinde lineer regülatörlere göre çok daha yüksek verimlilik ve daha az ısı kaybı.
*   **Filtreleme:** Giriş ve çıkışlarda kullanılan yüksek kapasiteli elektrolitik kondansatörler (470uF) ile voltaj dalgalanmaları (ripple) minimize edilmiştir.
*   **Koruma:** Schottky diyotlar (D1, D2) ile yüksek hızlı anahtarlama ve devre koruması sağlanmıştır.


<img width="1064" height="858" alt="image" src="https://github.com/user-attachments/assets/b999a996-25f8-4f1e-8e18-c119256955d2" />



> **Mühendislik Notu:** Bu modül; uçuş kontrol kartı, yardımcı bilgisayar (Raspberry Pi) ve servoların güç hatlarını birbirinden izole ederek, yüksek akım çeken motorların sensör verileri üzerinde oluşturabileceği elektriksel gürültüyü engellemektedir.
Rolüm ve Katkılarım
*   Elektronik ekip lideri olarak sistem tasarım süreçlerinin yönetilmesi.
*   Tüm alt sistemlerin (Güç, Haberleşme, Kontrol) entegrasyon şemasının çizilmesi.
*   Uçuş öncesi elektronik sistem testlerinin (failsafe, güç tüketimi, sinyal kalitesi) gerçekleştirilmesi.

**Tasarımcı:** Hüseyin Yuşa Sarı (YTÜ Elektronik ve Haberleşme Mühendisliği)

# Bilgisayar Ağları

## İçerik

- [Ch1 - Introduction](#introduction)
- [Ch2 - Application Layer](#application-layer)
- [Ch3 - Transport Layer](#transport-layer)
- [Ch4 - Network Layer:The Data Plane](#network-layer-the-data-plane)
- [Scaling Networks](scaling-networks)
- [Ch5 - Network Layer:Control Plane](#network-layer-control-plane)
- [Ch6 - The Link Layer and Lans](#the-link-layer-and-lans)
- [Cisco Packet Tracer](#cisco-packet-tracer)
- [Vize ve Final Hazırlık](vize_ve_final.md)

## Introduction

### 1. İnternet Nedir?

**Tanım:** İnternet, dünya çapındaki milyonlarca bilgisayar ağının birbirine bağlanmasıyla oluşan **ağların ağı**dır. Küresel ve bölgesel internet servis sağlayıcıları (ISS) aracılığıyla tüm ağlar birleştirilir.

**Ana Bileşenler:**

**Hosts (Uç Sistemler):** İnternete bağlanan son kullanıcı cihazlarıdır (bilgisayarlar, akıllı telefonlar, sunucular). Web, e-posta gibi uygulamalar bu cihazlarda çalışır.

**İletişim Hatları:** Verinin fiziksel olarak taşındığı ortamlardır.

   - **Kablolu:** Fiber optik kablo, bakır kablo (koaksiyel, Ethernet), çift burgulu kablo.

   - **Kablosuz:** Radyo dalgaları (Wi-Fi, uydu).

**Bant Genişliği:** Bir iletişim hattının saniyede iletebileceği maksimum veri miktarıdır (birimi genellikle bit/saniye - bps). Veri transfer hızını doğrudan etkiler.

### 2. Ağ Donanımları ve Protokoller

**Anahtar (Switch):** Genellikle aynı yerel ağ (LAN) içindeki cihazları birbirine bağlamak için kullanılır.

**Yönlendirici (Router):** Farklı ağları birbirine bağlayan ve veri paketlerini hedef ağa yönlendiren cihazdır. İnternetin temel yapı taşıdır.

**Protokol (Protocol):** Ağdaki cihazların birbiriyle nasıl iletişim kuracağını belirleyen kurallar bütünüdür. Örneğin, bir mesajın formatı, gönderilme sırası, hata durumunda yapılacaklar gibi.

**İnternet Standartları:**

- **RFC (Request for Comments):** İnternet protokolleri ve teknolojileriyle ilgili resmi teknik dokümanlardır.

- **IETF (Internet Engineering Task Force):** İnternet protokollerini geliştiren ve standartlaştıran kuruluştur.

### 3. Uygulama ve Servisler

**Uygulamalar:** E-posta (Outlook, Gmail), web tarayıcıları (Chrome, Firefox), oyunlar, VoIP (Skype) gibi son kullanıcıların kullandığı yazılımlardır.

**Servisler:** Uygulamalara veri iletimi için programlama arayüzü (API) sağlayan alt yapılardır. Örneğin, bir e-posta programının posta göndermek için kullandığı arka plan servisi.

**Sunucular (Servers):** Veri merkezlerinde bulunan, web sitelerini, e-postaları veya uygulamaları barındıran güçlü bilgisayarlardır.

### 4. Ağ Çekirdeği (Network Core)

**Ağ Çekirdeği:** Yönlendiricilerden (router) oluşan ve veri paketlerinin hedefe iletilmesini sağlayan merkezi yapıdır.

**İki Temel Anahtarlama Yöntemi:**

- **Devre Anahtarlama (Circuit Switching):**

    - İki cihaz iletişime geçmeden önce, uçtan uca bir yol (devre) tahsis edilir. Bu yol, iletişim boyunca sadece bu iki kullanıcıya özeldir.

    - Paylaşım yoktur, hat boş olsa bile başkası kullanamaz.

    - **Örnek**: Eski tip telefon santralleri.

    - **Çoğullama Yöntemleri (Daha fazla kullanıcıya hizmet için):**

        - **FDM (Frekans Bölmeli Çoğullama):** Her kullanıcıya farklı bir frekans bandı atanır.

        - **TDM (Zaman Bölmeli Çoğullama):** Kullanıcılara belirli zaman dilimleri (slot) tahsis edilir. Veri transferi sadece bu zaman dilimlerinde yapılır.

- **Paket Anahtarlama (Packet Switching):**

    - Gönderilecek veri küçük parçalara (paketlere) bölünür. Her paket ağda bağımsız olarak hedefe iletilir.

    - Ağ kaynakları (yönlendirici bağlantıları) paylaşımlıdır. Paketler sıraya girerek aynı hattı kullanır.

    - **Avantajı:** Kaynakların verimli kullanılması.

    - **Dezavantajı:** Aşırı yüklenme durumunda gecikme ve paket kaybı yaşanabilir.

### 5. Gecikme (Delay), Kayıp ve Veri Hızı

**Paket İletiminde Gecikme Türleri:**

- **İşlem Gecikmesi (Processing Delay):** Yönlendiricinin paketin başlığını incelemesi, bit hatalarını kontrol etmesi ve paketi hangi çıkış hattına yönlendireceğine karar vermesi için geçen süre.

- **Kuyruk Gecikmesi (Queueing Delay):** Paketin, çıkış hattına iletilmek için yönlendiricideki kuyrukta bekleme süresidir. Ağdaki yoğunluğa göre değişkendir.

- **İletim Gecikmesi (Transmission Delay):** Yönlendiricinin paketin tüm bitlerini çıkış hattına göndermesi için geçen süredir.

    - **Formül:** `L (paket boyutu, bit) / R (bağlantı hızı, bit/sn)`

        **Yayılma Gecikmesi (Propagation Delay):** Bir bitin, iletişim hattı üzerinden kaynaktan hedefe ulaşması için geçen süredir. Ortamın fiziksel özelliklerine (örneğin ışık hızı) ve mesafeye bağlıdır.

**Traceroute:** Bir bilgisayardan hedef bir cihaza giden yoldaki tüm yönlendiricileri ve her birine gidiş-dönüş süresini gösteren bir ağ tanılama aracıdır. (Genellikle her bir yönlendiriciye 3 paket gönderir).

**Paket Kaybı (Packet Loss):** Bir yönlendiricideki kuyruk (buffer) tamamen dolduğunda, yeni gelen paketlerin atılmasıdır.

**Verim (Throughput):** Kaynaktan hedefe birim zamanda başarıyla iletilen veri miktarıdır (bps). Genellikle yol üzerindeki en düşük kapasiteli bağlantı tarafından sınırlanır.

### 6. İletişim Ortamları (Media)

**Kılavuzlu Ortam (Guided Media):** Sinyallerin fiziksel bir kablo içinde iletilmesi.

- **Koaksiyel Kablo (Coaxial Cable):** Eski tip uydu ve TV kabloları. Çift yönlü veri iletimi ve çoklu kanal desteği vardır.

- **Fiber Optik Kablo (Fiber Optic Cable):** İnce cam tellerden oluşur. Işık sinyalleriyle veri iletir.

    - **Avantajları:** Çok yüksek hız, elektromanyetik gürültüden etkilenmez, sinyal zayıflaması çok düşüktür.

    - **Dezavantajı:** Veri iletimi genellikle tek yönlüdür (çift yönlü iletişim için iki kablo gerekir).

**Kılavuzsuz Ortam (Unguided Media):** Sinyallerin havada (kablosuz) iletilmesi.

- **Radyo Dalgaları (Wireless):** Antenler aracılığıyla manyetik dalgalar kullanılarak veri iletilir (Wi-Fi, uydu).

### 7. Katmanlı Mimari (Protocol Layers)

Karmaşık ağ sistemlerini daha kolay yönetmek ve anlamak için katmanlara ayrılır.

**İnternet Protokol Yığını (Internet Protocol Stack):** (Yukarıdan aşağıya)

1. **Uygulama Katmanı (Application):** Kullanıcı uygulamalarının ve protokollerin bulunduğu katmandır. (HTTP, SMTP, FTP)

2. **Taşıma Katmanı (Transport):** Uygulamalar arası veri iletimini sağlar. (TCP, UDP)

3. **Ağ Katmanı (Network):** Paketlerin kaynaktan hedefe yönlendirilmesini sağlar. (IP - Internet Protocol)

4. **Bağlantı Katmanı (Link):** Aynı ağdaki (örneğin bir Ethernet ağı) iki cihaz arasında veri iletimini sağlar.

5. **Fiziksel Katman (Physical):** Bitlerin (0 ve 1) kablo veya kablosuz ortam üzerinden elektrik/ışık/radyo sinyali olarak iletilmesiyle ilgilenir.

**OSI Referans Modeli:** 7 katmanlı teorik bir modeldir. İnternet modelinden farklı olarak şu iki katmanı da içerir:

- **Sunum Katmanı (Presentation):** Verinin şifrelenmesi/şifresinin çözülmesi, sıkıştırılması/açılması gibi veri formatlarıyla ilgilenir.

- **Oturum Katmanı (Session):** Uygulamalar arasındaki oturumların (bağlantıların) kurulması, yönetilmesi ve sonlandırılmasıyla ilgilenir. Kontrol noktaları (checkpoint) oluşturabilir.

**Kapsülleme (Encapsulation):** Gönderici tarafta, bir uygulama mesajı (veri) yukarıdan aşağıya her katmandan geçerken, o katmana ait bir başlık (header) bilgisi eklenir. Alıcı tarafta ise bu başlıklar aşağıdan yukarıya doğru tek tek çıkarılır (kapsülden çıkarma).

### 8. Ağ Güvenliği (Network Security)

Bilgisayar ağlarına yönelik saldırıları tespit etmek ve önlemek için güvenlik mimarileri gereklidir.

**Kötü Amaçlı Yazılımlar (Malware):**

- **Spyware:** Kullanıcının haberi olmadan özel bilgilerini (şifre, kredi kartı no) toplayan yazılım.

- **Solucan (Worm):** Kendini kopyalayarak ağ üzerinden diğer bilgisayarlara yayılan ve genellikle ağı yavaşlatan veya erişimi engelleyen yazılım.

**Saldırı Türleri:**

- **DoS (Denial of Service - Hizmet Engelleme):** Bir sunucuya aynı anda çok fazla gereksiz istek göndererek, sunucunun kaynaklarını tüketmek ve gerçek kullanıcıların hizmet alamamasını sağlamak.

- **Dinleme (Sniffing - Packet Capture):** Ağ trafiğini pasif olarak izleyerek, ağ üzerinden geçen verilerin (şifre, e-posta vb.) kopyalanması.

- **IP Sahteciliği (IP Spoofing):** Bir saldırganın, güvenilir bir kaynakmış gibi görünmek için gönderdiği paketlerin kaynak IP adresini değiştirmesi.
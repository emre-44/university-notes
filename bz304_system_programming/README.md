# System Programming

## İçerik
- [Linux Temel Komutlar](#linux-temel-komutlar)
- [Diğer Komutlar](#diğer-komutlar)

## Linux Temel Komutlar

**pwd:**(print working directory) O anda içinde bulunduğunuz dizinin tam yolunu gösterir.  
**ls:** (list) Bulunduğunuz dizindeki dosya ve klasörleri listeler.  
**cd:** (change directory) Dizin değiştirmek için kullanılır.  
**mkdir:** (make directory) Yeni bir klasör (dizin) oluşturur.  
**touch:** Yeni bir boş dosya oluşturur veya varolan bir dosyanın son değiştirilme tarihini günceller.  
**nano:** Terminal üzerinden kullanılan, basit ve popüler bir metin düzenleyicisidir. Bir dosyayı düzenlemek için nano dosya.txt yazabilirsiniz.  
**cat:** (concatenate) Bir dosyanın içeriğini terminal ekranında gösterir. Ayrıca birden fazla dosyayı birleştirmek için de kullanılır.  
**cp:** (copy) Dosya veya klasörleri kopyalamak için kullanılır.  
**move:** Bu genellikle mv komutudur. Dosya veya klasörleri taşımak veya yeniden adlandırmak için kullanılır.  
**rm:** (remove) Dosya veya klasörleri silmek için kullanılır.  

**clear:** Terminal ekranını temizler.  
**history:** Terminalde daha önce girdiğiniz komutların geçmişini listeler.  
**date:** Sistemin o anki tarih ve saat bilgisini gösterir.  
**man:** (manual'ın kısaltması) Bir komutun kullanım kılavuzunu (yardım dökümanını) gösterir.  
**echo:** Ekrana yazı yazdırmak için kullanılır.  

## Diğer Komutlar

**more:** Uzun dosyaları sayfa sayfa görüntülemenizi sağlar. Dolduğunda durur, boşluk tuşuyla bir sonraki sayfaya geçersiniz.  
**less:** more komutunun gelişmiş versiyonudur. Dosyaları sayfa sayfa gösterir ama aynı zamanda sayfada yukarı/aşağı kaymanıza ve arama yapmanıza da izin verir.  
**head:** Bir dosyanın sadece ilk 10 satırını gösterir. (Farklı sayıda satır görmek için -n seçeneği eklenir.)  
**tail:** Bir dosyanın sadece son 10 satırını gösterir. Canlı olarak güncellenen dosyaları (log dosyaları gibi) takip etmek için -f seçeneğiyle de kullanılır.  
**uname:** (unix name) İşletim sistemi hakkında temel bilgiler verir. Çekirdek (kernel) adı, sürümü gibi. Tek başına yazılırsa sadece "Linux" yazar. Detaylı bilgi için uname -a kullanılır.  
**top:** Sistemde o anda çalışan işlemleri (process'leri) canlı olarak gösterir. CPU, RAM kullanımını ve hangi işlemin ne kadar kaynak tükettiğini görmenizi sağlar.  
**df:** (disk free) Disklerin boş ve kullanılan alan miktarını gösterir.  
**lscpu:** İşlemciniz (CPU) hakkında detaylı bilgi verir. Kaç çekirdek olduğu, mimarisi, hızı gibi.  
**whoami:** O anda sistemde hangi kullanıcıyla işlem yaptığınızı gösterir.  

**ls -ltr:**

- **ls:** Listele.
- **-l:** (long) Detaylı liste (izinler, boyut, tarih vs.).
- **-t:** (time) Tarihe göre sırala (yeni olan önce).
- **-r:** (reverse) Ters sırala (eski olan önce).  

Sonuç: Dosyaları, en eskiden en yeniye doğru, detaylı olarak listeler.

**ls -a:**
- **-a:** (all) Tüm dosyaları göster.

Sonuç: Gizli dosyaları da (adı nokta ile başlayanlar) göstererek listeler.

**cp -pr:**
- **cp:** Kopyala.
- **-p:** (preserve) Orijinal dosyanın tüm özelliklerini (sahibi, zaman damgası, izinler) koru.
- **-r:** (recursive) Klasör kopyalarken, içindeki her şeyiyle beraber kopyala.

Sonuç: Bir klasörü, içindeki her şeyle ve tüm özelliklerini koruyarak kopyalar.

**rm -r:**
- **rm:** Sil.
- **-r:** (recursive) Klasör silerken içindeki her şeyiyle beraber sil.

Sonuç: Bir klasörü ve içindeki tüm dosya/alt klasörleri siler. (DİKKAT: Geri dönüş yoktur!)

**cat -n:**

- cat: Dosya içeriğini göster.
- -n: (number) Tüm satırları numaralandır.

Sonuç: Bir dosyanın içeriğini satır numaralarıyla birlikte ekrana yazar.

**head -n:**  Genel kullanımı head -n 20 dosya.txt şeklindedir. Bu da bir dosyanın ilk 20 satırını gösterir.

**tail -n:** Bir dosyanın son "n" satırını gösterir. Örnek: tail -n 20 dosya.txt (son 20 satırı gösterir).

**df -kh:**

- df: Disk alanını göster.
- -k: (kilobytes) Boyutları kilobayt cinsinden göster.
- -h: (human-readable) Boyutları insanın okuyabileceği formatta (MB, GB olarak) göster.

Sonuç: Disk kullanımını, anlaşılır formatta (KB/MB/GB) listeler.

**find:** Dosya veya klasör aramak için kullanılan çok güçlü bir komuttur. Örnek: find /home -name "resim.png" (home dizini altında resim.png adlı dosyayı ara).
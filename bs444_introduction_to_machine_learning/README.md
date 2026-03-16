# Machine Learning

## İçerik
- [Giriş](#giriş)

## Giriş
Machine learningin çıkış noktası turing testine dayanır.  

**Turing Testi: "Zeka"nın Tanımını Değiştirdi**

1950 yılında Alan Turing, "Düşünen makineler yapabilir miyiz?" sorusunun çok felsefi ve içinden çıkılmaz olduğunu fark etti. Bunun yerine daha basit bir ölçüt önerdi: "Bir makine, bir insanı, kendisinin de insan olduğuna ikna edebiliyorsa, o makine zekidir."

Bu test, yapay zekanın amacını netleştirdi: İnsan Davranışını Taklit Etmek. Artık amaç, insan gibi konuşan, insan gibi tepki veren sistemler yapmaktı.

**"Öğrenme" Fikri Doğdu**

Bir makineye tüm dünya bilgisini ve dil kurallarını tek tek öğretmek imkansızdı. İşte bu tıkanma noktasında, bilim insanları şunu fark etti: "Bir bebek nasıl zeki oluyor? Doğduğunda hiçbir şey bilmiyor, zamanla deneyimleyerek, örnekler görerek öğreniyor."

Eğer bir makine Turing Testi'ni geçecek kadar insan gibi davranacaksa, ona her şeyi öğretmek yerine, öğrenmeyi öğretmek daha mantıklıydı. İşte Machine Learning (Makine Öğrenmesi) tam olarak buradan doğdu:

**Amaç:** Makineye katı kurallar vermek değil, ona binlerce örnek (konuşma metni, resim, vs.) gösterip, bu örneklerdeki desenleri (pattern) kendi kendine bulmasını sağlamak.

**Mantık:** "İnsan gibi cevap verebilmesi için, önce insanların nasıl cevap verdiğini gözlemlemeli."

Üç öğrenme görecez:
1. Danışmanlı Öğrenme (Sınıflandırma ve tahmin)
2. Danışmansız Öğrenme (Kümeleme)
3. Takviyeli Öğrenme (Tüm otonom sistemler böyle çalışır.)

Transfer öğrenmesi popüler ama bu derste işlenmiyecek.

**Neden Makine öğrenmesi?**
- Teknolojiye herkes ulaşabilir.
- Yeni ve güçlü algoritmalar.
- Veri boyutu ve parametre sayısı arttı.
- Otonom sistemlere talep var.
- Fonksiyonel tıpta kullanılıyor.

**Makine Öğrenmesi Uygulamaları**
- Veri Madenciliği
- Programlanması zor yazılım uygulamaları
- Kişileştirilmiş uygulamalar

**Makine öğrenmesinin bugünü ve geleceği**  
**Data Fusion** (Veri Füzyonu/Tümleştirmesi), birden fazla kaynaktan gelen veriyi birleştirerek, tek bir kaynaktan elde edilemeyecek kadar doğru, tutarlı ve anlamlı bilgi üretme sürecidir.  

- Örneğin bir otonom araç düşünün:

 - Kamera: "Önümde yuvarlak, kırmızı bir cisim var." (diyelim)
 - Lidar (lazer tarayıcı): "Önümde 15 metre uzaklıkta, hareket eden bir nesne var." (diyelim)
 - GPS: "Şu an bir kavşaktayım." (diyelim)

Fusion olmazsa: Kamera yuvarlak cismin bir trafik konisi mi yoksa dur işareti mi olduğunu tam çıkaramayabilir.

**İlişkili Disiplinler**  
- Linguistic

**Makine Öğrenmesi Nedir?**  
Tom Mitchell'ın tanımı şöyledir:
 - Bir bilgisayar programının, E tecrübesinden (Experience) yola çıkarak, P performans ölçütüne (Performance) göre, T görevinde (Task) başarısı artıyorsa, o program öğreniyor denir.

Bu üç kavram (T, P, E) aslında öğrenme sürecinin 3 ana bileşenidir.

**Öğrenme Sistemi Tasarımı**
1. Eğitim tecrübesi seçimi
2. Hedef fonksiyon seçimi

**Sınıflandırma ve Regresyon farkı**  
Hedef değişkenim **kategorik** (spam/spam değil, hasta/sağlıklı) ise **Sınıflandırma**, **sayısal** (fiyat, sıcaklık, boy) ise **Regresyon** kullanırım.

| Özellik | Sınıflandırma | Regresyon |
| :--- | :--- | :--- |
| **Tahmin Ettiği Şey** | Kategori / Sınıf / Etiket | Sayı / Değer / Miktar |
| **Örnek Çıktılar** | "Kedi", "Köpek", "Spam", "Spam Değil", "Hasta", "Sağlıklı" | 150.000 TL, 25°C, 75 km/sa, 3.5 yaş |
| **Sorduğu Soru** | Bu hangi gruba ait? / Bu nedir? | Bu ne kadar? / Kaç tane? / Ne değerde? |

## Kavram Öğrenmesi

## Karar Ağaçları
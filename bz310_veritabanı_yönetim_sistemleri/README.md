# Veritabanı Yönetim sistemleri

# İçerik
- [Temel Kavramlar](#temel-kavramlar)  
- [Veritabanı Tasarımı](#veritabanı-tasarımı)  
- [Er Diyagramı](#er-diyagrami)  
- [Veritabanı Normalizasyonu](#veritabanı-normalizasyonu)  
- [İlişkisel Cebir](#ilişkisel-cebir)  
- [SQL ve DDL ](#sql-ve-ddl)  
- [SQLde Aritmetik Operatorler ve Fonksiyonlar](#sqlde-aritmetik-operatorler-ve-fonksiyonlar)  
- [SQLde Alt Sorgular](#sqlde-alt-sorgular)
- [SQLde View](#sqlde-view)  
- [SQL Transaction Yönetimi](#sql-transaction-yönetimi)  
- [Btree](#btree)  
- [Sorgu Optimizasyonu](#sorgu-optimizasyonu)  

## Temel Kavramlar
Sıralı Erişimli Dosyalar = Static Array  
Doğrudan Erişimli Dosyalar = Dynamic Array  

### Veritabanı Nedir?  
**Veri tabanı**, yapılandırılmış bir şekilde organize edilmiş ve depolanmış veri koleksiyonudur.  

**Tablo** Veritabanı içerisinde tutulacak verileri depolamak için kullanılır.  
**Satır**lar kayıtları (record) gösterir.  
**Sütun**lar veri türlerini gösterir  
**Anahtar** kayıtlar içerisinde benzersiz olan sütun veya sütun grubudur.  

**Birincil Anahtar ( Primary Key)** Benzersiz yani aynı değeri iki kez içermeyecek olan sütunlardir. 
NULL(boş) veya birbirinin aynı olan değerleri içeremez.  

**İkincil Anahtar (Foreign Key)** İki tablo arasında bağlantı (ilişki) varsa bir tablodaki bir sütun diğer tablonunun birincil anahtarı ise bu sütuna ikincil anahtar denilir.  

---

<br>

![Tablo Örneği](./images/ornek_tablosu.png)

---

<br>

**İlişkilendirme(join)** Tek sorgu ile birden fazla tablodan bilgi alama işlemine ilişkilendirme denilir.  

Farklı join türleri vardır:  
- Inner Join  
- Left Outer Join  
- Right Outer Join  
- Full Outer Join

---

<br>

![Tablo Örneği](./images/iliskilendirme_ornek.png)

---

<br>

### Veritabanı Yönetim Sistemleri ###  

**Veritabanı yönetim sistemleri** (Database Management Systems) veri tutmak amacıyla yeni veritabanı oluşturmak, var olan veri tabanı üzerinde değişiklik yapmak, veritabanın bakımı ve yedeklenmesi, tablolar arasında ilişki kurmak, kullanıcı yetkilerini belirlemek amacıyla kullanılan yazılımlardır.  

**Veritabanı Yönetim Sistemleri Faydaları**  
- Veri tekrarı (Data Redundancy) engellenir.  
- Veri Tutarlılığı (Data Consistency)  
- Veri Paylaşımı (Data Concurrency)  
- Veri Bütünlüğü (Data Integrity)    
- Veri Güvenliği (Data Security)  
- Veri Bağımsızlığı (Data Independecy)  

**Veritabanı Kullanıcıları**  
- Veritabanı Yöneticisi (Database Administrator)  
- Uygulama Programcısı  
- Sorgu Dili KUllanıcıları  
- Son Kullanıcılar  

<br>

## **Veritabanı Tasarımı**

**Veritabanı tasarımında takip edilecek adımlar**  
- Depolanacak verilerin belirlenmesi  
- Tabloların oluşturulması  
- Anahtar sütunların belirlenmesi  
- Tabloların bölünmesi (gerekirse)   
- İlişkilerin kurulması  

**Kavramsal Tasarım**  
- En çok kullanılan model ER (Entity-Relationship,Varlık-İlişli) modelidir.  
- Veritabanının şematik olarak tasarımıdır.  

**Varlık Kavramı**  
- Modelin en temel öğesidir.  
- Var olan ve benzerlerinden ayrılan her şey varlıktır.  

**Nitelik Kavramı**
- Varlıkların her bir özelliği nitelektir.  
- *Anahtar Nitelik*: Değeri her varlık için farklı olan niteliktir. Şemada altı çizilerek gösterilir.  

**Domain(Etki Alanı)**  
- Niteliklerin alabileceği değer aralığıdır.  
- Er diyagramınad gösterilmez  

**İlişki**  
- Farklı varlıklar arasındaki ilişkileri ifade eder.  
- Model içerisinde baklava dilimi ile gösterilir.  
- İlişkiler 1-1,1-n,n-m olabilir.  

---

<br>

![tablo örneği](./images/iliski_ornekleri.png)

---

<br>

![tablo örneği](./images/tekrarli_iliski.png)

---

<br>

### Bire-bir (1-1) İlişkinin tabloya dönüştürülmesi
İlişkide bir varlık kümesinin birincil anahtarı diğer varlık kümesinin yabancı (ikincil) anahtarı olur. 

![tablo örneği](./images/bire_bir_iliski.png)

---

<br>

### Bire-Çok veya Çoğa-Bir (1-n, n-1) İlişkilerin Tabloya Dönüştürülmesi
İlişkinin n tarafındaki tabloya 1 tarafındaki tablonun birincil anahtarı yabancı anahtar olarak eklenir.

![tablo örneği](./images/bire_n_iliski.png)

---

<br>

### Çoğa-Çok (n-m) İlişkilerin Tabloya Dönüştürülmesi  
İlişkiyi oluşturan tabloların birincil anahtarları ilişiki oluşturan tabloya yabancı anahtar olarak eklenir.  
İlişkiden oluşturulan tablonun birincil anahtarı oluşturulan yabancı anahtarların birleşiminden oluşur. Eğer bu ihtiyaca cevaba vermez ise yeni sütun eklenerek birincil anahtar yapılır. 

![tablo örneği](./images/coka_cok_iliski.png)

---

<br>

![tablo örneği](./images/degerli_nitelik_tablosu.png)

--- 
<br>

![tablo örneği](./images/zayif_varlik_tablosu.png)


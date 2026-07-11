# 📊 Data Science SQL Project 3 - Relational Database, Aggregation & Joins

Bu projede, PostgreSQL üzerinde ilişkisel veritabanı (Relational Database) mimarisi kurarak gelişmiş veri analizi, çoklu tablo birleştirme (JOIN) ve toplulaştırma (Aggregation) çalışmaları gerçekleştirdim. Proje kapsamında verilerin şemalar halinde izole edilmesi, tarih manipülasyonları ve ilişkisel köprü tabloları üzerinden analitik sorgular üretilmiştir.

---

## 🛠️ Teknolojiler ve Veritabanı Mimarisi

* **Veritabanı:** PostgreSQL
* **Şema Yönetimi:** Proje nesnelerinin `public` şeması ile karışmaması adına `data3` isimli özel bir şema (Schema) oluşturulmuş ve `ALTER USER postgres SET search_path TO data3, public;` komutuyla arama yolu kalıcı olarak optimize edilmiştir.

### Veri Modeli ve İlişkiler
Proje, birbiriyle ilişkili 3 temel tablonun yönetimi üzerine kurulmuştur:
* `students`: Öğrenci demografik ve yaş bilgileri.
* `courses`: Açılan kurslar ve kategorileri.
* `enrollments`: Öğrencilerin kurslara kayıt geçmişini tutan, yabancı anahtarlarla (`FOREIGN KEY`) bağlı ilişkisel köprü tablosu.

---

## 🚀 Projede Çözülen Analitik Problemler ve Kazanımlar

Yazdığım sorgularla aşağıdaki SQL yetkinlikleri üzerine pratik çözümler geliştirilmiştir:

1. **Zaman Serisi ve Tarih Fonksiyonları:**
   * `DATE_TRUNC` ile kayıtlar ay bazında yuvarlanarak kronolojik trend analizi yapıldı.
   * `DATE_PART` fonksiyonu kullanılarak kayıt tarihlerinden sadece yıl bilgisi izole edildi.

2. **Toplulaştırma (Aggregate) Fonksiyonları:**
   * `SUM`, `COUNT`, `MIN` ve `AVG` fonksiyonları aktif şekilde kullanılarak; toplam yaş, kurs sayıları, en eski kayıt tarihleri ve en genç öğrenci tespiti gibi metrikler hesaplandı.
   * Filtreleme operasyonlarında statik eşikler kullanılarak veri kümesi başarıyla analiz edildi.

3. **Gelişmiş Çoklu Tablo Birleştirmeleri (JOIN + GROUP BY):**
   * Üç tablo (`courses`, `enrollments`, `students`) birbirine `JOIN` mekanizmalarıyla bağlanarak ders bazlı öğrenci sayısı ve yaş ortalamaları hesaplandı.
   * `DISTINCT` ve `RIGHT JOIN` yapıları kullanılarak mükerrer kayıtlar önlendi ve kayıt olunmuş derslerin isimleri tekrarsız olarak listelendi.

---

## 💻 Projeyi Yerelde Çalıştırma

1. Projeyi klonlayın ve bağımlılıkları yükleyin:
   ```bash
   pip install -r requirements.txt

# Ürün Benzerlik Analizi ve Tavsiye Sistemi (Text Mining Kullanılarak)

Amazon ürünleri için **TF-IDF** ve **kosinüs benzerliği** kullanarak içerik tabanlı bir öneri sistemi. Ürün başlıkları ve açıklamalarına göre benzer ürünleri önerir.

---

## 📌 Proje Özeti

Bu proje, Amazon ürünleri için **içerik tabanlı bir öneri sistemi** uygular. Sistem, ürün açıklamaları üzerinden ürün benzerliklerini hesaplar ve her ürün için en benzer N ürünü önerir.

---

## 🛠 Özellikler ve Yöntem

### Veri İşleme
- Birden fazla kategoriden gelen **JSONL dosyaları** tek bir DataFrame’de birleştirildi.  
- Ürün detayları (örn. marka, malzeme) yapılandırılmış metin hâline getirildi.  
- Metin temizlendi: noktalama işaretleri kaldırıldı, küçük harfe çevrildi, boşluklar düzeltildi.

### Özellik Mühendisliği
- **TF-IDF vektörizasyonu** uygulandı:  
  - N-gramlar: **tekli ve ikili kelimeler (unigram + bigram)**  
  - Stop-word (önemsiz kelime) çıkarımı  
  - Maksimum özellik = **10.000** (en anlamlı terimlere odaklanmak için)

### Benzerlik Hesaplama
- Ürün açıklamaları arasında **kosinüs benzerliği** hesaplandı.  
- Öneriler için **14.000 x 14.000 benzerlik matrisi** oluşturuldu.

### Öneri Fonksiyonu
- Belirli bir ürün için **en benzer N ürünü** kosinüs benzerlik skorlarına göre getirir.

---

## 📊 Değerlendirme ve İçgörüler

- **Öneri Kalitesi**:  
  - **Kozmetik ve kişisel bakım ürünlerinde** iyi çalışır.  
  - **Dijital Müzik** kategorisinde metinlerin az ve genel olmasından dolayı zorlanır.  

- **Benzerlik Dağılımı**:  
  - Çoğu ürün **0.1–0.3** arası skor aldı  
  - Bazı ürün çiftleri **>0.5**, güçlü eşleşmeler gösteriyor  

- **Görselleştirmeler**:  
  - Isı haritaları ve histogramlar kümeleşme ve skor dağılımını gösterir  

---

## ⚠ Sınırlamalar ve Geliştirmeler

- Bazı kategorilerde açıklamaların az veya genel olması doğruluk oranını düşürür.  
- **Geliştirmeler**:  
  - Kullanıcı davranış verilerini (puanlar, satın almalar) ekleyerek **hibrit öneri sistemi** oluşturmak  
  - Daha derin semantik analiz için **Word2Vec, BERT gibi kelime gömme yöntemleri** kullanmak  
  - **Soğuk başlangıç (cold-start) problemlerini** popülerlik tabanlı önerilerle çözmek  

---

## 💻 Kullanılan Teknolojiler

- **Python Kütüphaneleri**: Pandas, Scikit-learn (TF-IDF, kosinüs benzerliği), Matplotlib / Seaborn  
- **Yöntemler**: Metin ön işleme, TF-IDF, kosinüs benzerliği, ısı haritası görselleştirmesi  

---


## 👤 FURKAN DMEİR 
Geliştiren: **FURKAN DEMİR ** 


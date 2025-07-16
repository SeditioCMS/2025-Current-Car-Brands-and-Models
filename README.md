# 2025-Güncel-Araba-Markalar-ve-Modelleri

📦 **2025 Güncel Araba Markaları ve Modelleri Veritabanı**

Bu proje, 2025 yılına ait **en güncel otomobil marka, model, alt model ve donanım seçeneklerini** içeren detaylı bir SQL veritabanı sunar. Oto ekspertiz, araç karşılaştırma, araç listeleme, galeri ve teknik inceleme gibi projelerde kullanılabilir.

---

## 🔗 Satın Alma

Veritabanını hemen satın almak için:

👉 [https://dijitalsite.com.tr/2025-arac-marka-model-sql-veritabani](https://dijitalsite.com.tr/2025-arac-marka-model-sql-veritabani)

---

## 📁 İçerik

Veritabanı şu bilgileri kapsamaktadır:

- ✅ 350+ Araba Markası  
- ✅ 10.000+ Model ve Alt Model  
- ✅ Donanım ve Seçenek Bilgileri  
- ✅ Üretim Yılları  
- ✅ Kullanıma hazır SQL yapısı (InnoDB, utf8mb4)

---

## 🧩 Kullanım Alanları

Bu veritabanı, aşağıdaki alanlar için uygundur:

- Oto Ekspertiz Programları  
- Araç Teknik Özellik Siteleri  
- İkinci El Araç Platformları  
- Rent A Car Yazılımları  
- Araç Karşılaştırma Sistemleri  
- Otomobil Haber Siteleri  

---

## 🛠 Örnek Tablo Yapısı

```sql
-- Marka Tablosu
CREATE TABLE marka (
  id INT AUTO_INCREMENT PRIMARY KEY,
  marka_adi VARCHAR(100),
  marka_alias VARCHAR(100),
  logo_url VARCHAR(255)
);

-- Model Tablosu
CREATE TABLE model (
  id INT AUTO_INCREMENT PRIMARY KEY,
  marka_id INT,
  model_adi VARCHAR(100),
  model_alias VARCHAR(100),
  FOREIGN KEY (marka_id) REFERENCES marka(id)
);

-- Alt Model Tablosu
CREATE TABLE alt_model (
  id INT AUTO_INCREMENT PRIMARY KEY,
  model_id INT,
  alt_model_adi VARCHAR(100),
  alt_model_alias VARCHAR(100),
  baslangic_yili INT,
  bitis_yili INT,
  FOREIGN KEY (model_id) REFERENCES model(id)
);

-- Seçenekler (Donanım) Tablosu
CREATE TABLE model_secenekler (
  id INT AUTO_INCREMENT PRIMARY KEY,
  marka_id INT,
  model_id INT,
  alt_model_id INT,
  secenek_adi VARCHAR(100),
  secenek_alias VARCHAR(100)
);

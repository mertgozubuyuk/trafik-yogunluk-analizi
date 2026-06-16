# 🚦 Video Segmentasyonu ile Akıllı Trafik Yoğunluğu Analizi

Lineer cebir tabanlı video segmentasyonu ve Karar Destek Sistemi (KDS) kullanarak 
kavşaklardaki trafik yoğunluğunu gerçek zamanlı analiz eden ve sinyalizasyon sürelerini 
dinamik olarak optimize eden bir sistem.

---

## 📌 Proje Hakkında

Bu proje, Beykoz Üniversitesi Lineer Cebir dersi kapsamında geliştirilmiştir.  
Sabit açılı bir trafik kamerasından alınan video akışı, matris tabanlı yöntemlerle 
işlenerek araçlar arka plandan ayrıştırılmış ve anlık yoğunluk oranı hesaplanmıştır.  
Elde edilen veriler bir Karar Destek Sistemi'ne aktarılarak trafik ışığı süreleri 
dinamik biçimde optimize edilmiştir.

---

## 🧮 Kullanılan Yöntemler

- **Gri Seviye Dönüşümü:** `Gray = 0.299R + 0.587G + 0.114B`
- **Ardışık Kare Farkı:** `D = |Aₜ - Aₜ₋₁|`
- **Eşikleme (Thresholding):** İkili maske matrisi üretimi
- **Frobenius Normu:** Hareket büyüklüğü ölçümü
- **KDS Karar Mekanizması:** Yoğunluk oranına göre dinamik sinyal süresi

---

## 🛠️ Kullanılan Teknolojiler

![Python](https://img.shields.io/badge/Python-3.x-blue)
![OpenCV](https://img.shields.io/badge/OpenCV-4.x-green)
![NumPy](https://img.shields.io/badge/NumPy-matematiksel%20işlemler-orange)
![Matplotlib](https://img.shields.io/badge/Matplotlib-görselleştirme-red)

---

## ⚙️ Nasıl Çalıştırılır?

1. Repoyu klonla:
```bash
   git clone https://github.com/mertgozubuyuk/trafik-yogunluk-analizi.git
```

2. Gerekli kütüphaneleri yükle:
```bash
   pip install opencv-python numpy matplotlib
```

3. Google Colab üzerinde aç:
   - `Trafik_Yogunluk_Analizi_Lineer_Cebir.ipynb` dosyasını Colab'a yükle
   - Trafik videonu `trafik_analizi.mp4` adıyla yükle
   - Hücreleri sırayla çalıştır

---

## 📊 Sistem Mimarisi

Ham Video → Ön İşleme → Matris Farkı → Segmentasyon → Yoğunluk Analizi → KDS Kararı

### KDS Karar Tablosu

| Yoğunluk Oranı (P) | Karar | Aksiyon |
|---|---|---|
| P > %10 | Çok Yoğun | Yeşil ışık süresini %50 artır |
| %5 < P ≤ %10 | Orta Yoğun | Yeşil ışık süresini %20 artır |
| P ≤ %5 | Standart | Süreyi koru |

---

## 📈 Performans Sonuçları

| Metrik | Değer |
|---|---|
| Kesinlik (Precision) | %88.4 |
| Duyarlılık (Recall) | %91.7 |
| F1 Skoru | %90.0 |
| Doğruluk (Accuracy) | %92.3 |

---

## 📄 Akademik Rapor

Projenin detaylı akademik raporu `rapor/` klasöründe yer almaktadır.

---

## 👤 Geliştirici

**Mert GÖZÜBÜYÜK**  
Beykoz Üniversitesi — 2504040157

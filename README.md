# 🛫 AOD-4 Airborne Objects Detection & Classification

Bu proje, **Akbank Derin Öğrenme Bootcamp (Eylül 2025)** kapsamında geliştirilmiştir.  
Amaç: Havada görülen cisimleri **(airplane, helicopter, drone, bird)** derin öğrenme yöntemleri ile **algılamak ve sınıflandırmak**.

---

## 📂 İçerik

- **YOLOv8** tabanlı nesne algılama modeli  
- **ResNet50** tabanlı sınıflandırma modeli  
- **Grad-CAM** ile modelin karar bölgelerinin görselleştirilmesi  
- Hiperparametre denemeleri (epoch / learning rate değişimleri)  
- Eğitim ve değerlendirme sonuçları (mAP50-95, precision, recall, Confusion Matrix)

---

## 🗂️ Veri Seti

- **Kaynak:** [AOD-4 (Airborne Objects Dataset)](https://www.kaggle.com/)  
- **Sınıflar:** `airplane`, `helicopter`, `drone`, `bird`  
- **Toplam:** ~22.5K görsel (train / valid / test split)  
- **Format:** YOLOv8 uyumlu (images + labels)  

> Verisetinin ham hali depoya eklenmemiştir; Kaggle üzerinden erişilebilir.

---

## 🛠️ Kullanılan Yöntemler

- **YOLOv8n** modeli ile transfer learning yapıldı.  
- Görüntüler 640×640 boyutuna ölçeklendi; veri artırma (augmentation) uygulandı.  
- **ResNet50** sınıflandırma modeli, AdamW optimizer ve dropout ile eğitildi.  
- **Grad-CAM** ile modelin hangi bölgelere odaklandığı görselleştirildi.  
- **mAP50-95 / Precision / Recall** metrikleri ve Confusion Matrix ile başarı ölçüldü.
---



## 📊 Sonuçlar

- YOLOv8 modeli temel konfigürasyonda tatmin edici **mAP50-95 / Precision / Recall** sonuçları verdi.  
- Confusion Matrix analizine göre en çok karışan sınıflar **drone ↔ bird** oldu.  
- **Grad-CAM** görselleştirmeleri modelin rotor / kanat / gövde bölgelerine odaklandığını gösterdi.  
- Overfitting belirgin değildir; ancak daha fazla epoch ve gelişmiş augmentation ile performans artışı mümkündür.

---

## 🚀 Kullanım Alanları

Bu model gerçek hayatta şu alanlarda kullanılabilir:

- **Hava sahası güvenliği:** Yetkisiz drone tespiti ve kuş çarpışma önleme sistemleri  
- **Yangın & afet izleme:** İnsansız hava araçları ve yangın söndürme uçaklarının takibi  
- **Askerî & sınır gözetimi:** Sivil ve askeri hava araçlarını ayırt etme  
- **Hava trafiği analizi:** Radar/ADS-B verilerinin görsel doğrulamasını destekleme

Bu sayede **hava sahası güvenliğini artırma** ve **otonom izleme sistemlerinin hassasiyetini yükseltme** gibi görevlerde kullanılabilir.

---

## 🧪 Çalıştırma

```bash
pip install ultralytics torch torchvision torchcam matplotlib


🔗 Kaggle Notebook
👉https://www.kaggle.com/code/nilaycoar/notebook1

# 🌍 Dünya Sağlık Örgütü (WHO) Yaşam Beklentisi Analizi ve Tahmini

Bu proje, ülkelerin sağlık, ekonomi ve demografik göstergelerini kullanarak **ortalama yaşam süresini (Life Expectancy)** yüksek doğrulukla tahmin eden bir makine öğrenmesi çalışmasıdır.

---

## 📌 Projenin Amacı
Bir ülkenin kalkınmışlık düzeyi, eğitim süresi ve sağlık harcamaları gibi değişkenlerin yaşam süresi üzerindeki etkisini analiz etmek ve bu değişkenler üzerinden bir regresyon modeli geliştirerek gelecek tahminlerinde bulunmaktır.

## 🧬 Veri Ön İşleme (Data Preprocessing)
Veri setindeki eksik değerler, verinin doğasına uygun bir hibrit strateji ile temizlenmiştir:

1. **Doğrusal İnterpolasyon (Linear Interpolation):** Sağlık ve ekonomi verileri zamansal bir süreç izlediği için, her ülkenin kendi içindeki eksik yılları kronolojik olarak doldurulmuştur.
2. **Statü Bazlı Medyan (Status-based Median):** Hiç verisi bulunmayan ülkeler için, ülkenin gelişmişlik durumu (`Developed` veya `Developing`) baz alınarak grup medyanları atanmıştır.
3. **Sütun Temizliği:** Sütun isimlerindeki gereksiz boşluklar temizlenerek veri manipülasyonu standart hale getirilmiştir.

---

## 📊 Görsel Veri Analizi (EDA)
Veriden elde edilen temel içgörüler ve değişkenler arası ilişkiler aşağıda sunulmuştur:

### 1. Korelasyon Isı Haritası
Değişkenler arasındaki pozitif ve negatif ilişkileri gösterir. Okullaşma ve gelir düzeyi ile yaşam süresi arasındaki güçlü bağ burada netçe görülmektedir.

### 2. Eğitim ve Yaşam Süresi İlişkisi
Okullaşma süresi arttıkça yaşam beklentisinin nasıl yükseldiğini gösteren saçılım grafiği.

### 3. Özellik Önem Sırası (Feature Importance)
Random Forest modelimizin tahmin yaparken hangi değişkenlere (HIV/AIDS, Yetişkin Ölüm Oranı vb.) daha çok ağırlık verdiğini gösterir.

## 🧬 Model Seçimi: Random Forest Regressor
Projede **Random Forest** algoritmasının tercih edilme nedenleri:
* Değişkenler arasındaki **doğrusal olmayan (non-linear)** ilişkileri yakalayabilmesi.
* Eğitim ve gelir düzeyi gibi değişkenlerin birbiriyle olan karmaşık etkileşimlerini analiz edebilmesi.
* Aykırı değerlere (outliers) karşı Linear Regression'a göre daha dayanıklı olması.

---

## 📈 Model Performansı ve Sonuçlar
Modelimiz test verileri üzerinde oldukça yüksek bir başarı sergilemiştir:

| Metrik | Değer | Açıklama |
| :--- | :--- | :--- |
| **R2 Skoru** | **%95.91** | Yaşam süresindeki değişimin %95'i modelce açıklanmaktadır. |
| **MAE** | **1.19 Yıl** | Ortalama tahmin hatamız sadece 14 aydır. |
| **RMSE** | **1.92 Yıl** | Büyük hataları daha net gösteren hata payı. |
| **MSE** | **3.68** | Hata kareleri ortalaması. |

---

## 📂 Dosya Yapısı
- `Life Expectancy Data.csv`: WHO'dan alınan ham veri seti.
- `analiz.ipynb`: Veri keşfi, ön işleme ve modelleme kodları.
- `Veri_Analizi_Final.pdf`: Çalışmanın detaylı akademik açıklaması ve görsel analizleri.

---

## 🚀 Kurulum ve Çalıştırma
Projenin yerel bilgisayarda çalıştırılması için:
1. Depoyu klonlayın: `git clone [GITHUB_URL_BURAYA]`
2. Gerekli kütüphaneleri yükleyin: `pip install pandas numpy seaborn matplotlib scikit-learn`
3. Jupyter Notebook dosyasını (`.ipynb`) herhangi bir editörde (VS Code vb.) açıp tüm hücreleri çalıştırın.

**Hazırlayan:** Sıla AKGÜN 23430070028



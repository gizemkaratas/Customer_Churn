# Müşteri Churn Tahmini Projesi

Bu proje, müşteri kaybını (churn) tahmin etmek amacıyla makine öğrenmesi yöntemlerini kullanarak veri analizi ve modelleme işlemlerini içermektedir. Proje, Telco-Customer-Churn veri setini kullanarak müşterilerin şirketten ayrılma olasılıklarını tahmin etmeye yönelik bir model geliştirmeyi hedeflemektedir.

## İçindekiler

1. [Proje Açıklaması](#proje-açıklaması)
2. [Veri Seti](#veri-seti)
3. [Veri Ön İşleme](#veri-ön-işleme)
4. [Analiz ve Görselleştirme](#analiz-ve-görselleştirme)
5. [Modelleme](#modelleme)
6. [Sonuçlar](#sonuçlar)
7. [Kullanılan Kütüphaneler](#kullanılan-kütüphaneler)

## Proje Açıklaması

Bu projede,  [Telco Customer Churn Dataset](https://www.kaggle.com/datasets/blastchar/telco-customer-churn) veri seti kullanılarak müşteri kaybını tahmin etmek için çeşitli makine öğrenmesi algoritmaları uygulanmıştır. Veri analizi, veri temizleme ve modelleme süreçleri adım adım ele alınmıştır.

## Veri Seti

Veri seti, müşteri bilgilerini içeren çeşitli özellikler sunmaktadır:

- **CustomerId**: Müşteri İD’si
- **Gender**: Cinsiyet
- **SeniorCitizen**: Yaşlılık durumu (1, 0)
- **Partner**: Ortağı olup olmadığı (Evet, Hayır)
- **Dependents**: Bakmakla yükümlü olduğu kişiler (Evet, Hayır)
- **Tenure**: Şirkette kaldığı ay sayısı
- **PhoneService**: Telefon hizmeti (Evet, Hayır)
- **MultipleLines**: Birden fazla hattı olup olmadığı (Evet, Hayır, Telefon hizmeti yok)
- **InternetService**: İnternet servis sağlayıcısı (DSL, Fiber optik, Hayır)
- **OnlineSecurity**: Çevrimiçi güvenlik (Evet, Hayır, İnternet hizmeti yok)
- **OnlineBackup**: Online yedekleme (Evet, Hayır, İnternet hizmeti yok)
- **DeviceProtection**: Cihaz koruması (Evet, Hayır, İnternet hizmeti yok)
- **TechSupport**: Teknik destek (Evet, Hayır, İnternet hizmeti yok)
- **StreamingTV**: TV yayını (Evet, Hayır, İnternet hizmeti yok)
- **StreamingMovies**: Film akışı (Evet, Hayır, İnternet hizmeti yok)
- **Contract**: Sözleşme süresi (Aydan aya, Bir yıl, İki yıl)
- **PaperlessBilling**: Kağıtsız fatura (Evet, Hayır)
- **PaymentMethod**: Ödeme yöntemi (Elektronik çek, Posta çeki, Banka havalesi (otomatik), Kredi kartı (otomatik))
- **MonthlyCharges**: Aylık tahsil edilen tutar
- **TotalCharges**: Toplam tahsil edilen tutar
- **Churn**: Müşterinin kullanıp kullanmadığı (Evet veya Hayır)

## Veri Ön İşleme

1. **Eksik Veriler**: `TotalCharges` sütunundaki veri tipini düzelttik. 
2. **Veri Temizleme**: 'No phone service' ve 'No internet service' değerlerini 'No' ile değiştirdik.
3. **Kategorik ve Sayısal Veriler**: Kategorik ve sayısal değişkenler ayrıştırıldı, veri dağılımları ve hedef değişken ile ilişkileri incelendi.

## Analiz ve Görselleştirme

Veri analizi ve görselleştirme aşamasında, veri dağılımları, kategorik değişkenlerin dağılımları ve hedef değişkenle ilişkileri incelenmiştir. Görselleştirme işlemleri, veri içindeki desenleri ve ilişkileri daha iyi anlamamıza yardımcı olmuştur.

## Model Performans Sonuçları

Aşağıdaki tablo, farklı makine öğrenmesi algoritmalarının performansını göstermektedir:

| Model                   | Accuracy           |
|-------------------------|---------------------|
| Logistic Regression     | 0.788               |
| Random Forest           | 0.787               |
| Support Vector Machine  | 0.790               |
| K-Nearest Neighbors     | 0.749               |

## Optimize Edilmiş SVM Metrikleri

Aşağıdaki tablo, optimize edilmiş SVM modelinin performans metriklerini göstermektedir:

| Metric         | Value                |
|----------------|----------------------|
| **Accuracy**   | 0.795                |
| **ROC AUC**    | 0.675                |
| **Recall**     | 0.434                |
| **Precision**  | 0.634                |

### Confusion Matrix

Aşağıda, optimize edilmiş SVM modelinin konfizyon matrisini bulabilirsiniz:


- **True Negatives (TN)**: 1445
- **False Positives (FP)**: 133
- **False Negatives (FN)**: 300
- **True Positives (TP)**: 230

### Açıklamalar

- **Accuracy**: Modelin genel doğru tahmin oranını gösterir.
- **ROC AUC**: Modelin sınıflandırma performansını, özellikle sınıflar arasındaki ayrımı değerlendirir.
- **Recall**: Pozitif sınıfları doğru şekilde tahmin etme yeteneğini ölçer.
- **Precision**: Modelin pozitif tahminlerinin ne kadar doğru olduğunu gösterir.

Confusion matrix, modelin doğru ve yanlış tahminlerini ayrıntılı olarak sunar.

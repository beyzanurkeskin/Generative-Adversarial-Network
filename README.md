# GAN ile BAF Veri Setinden Yapay Veri Üretimi

Bu projemde, Generative Adversarial Network (GAN) kullanarak BAF veri setinden sahte veriler üretmek üzerine çalıştım.
- **Tüm Staj Notları:** https://www.canva.com/design/DAGN59Iykzc/AQAPgHjoHkupfRnHfsHTkQ/edit?utm_content=DAGN59Iykzc&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton

## Proje Yapısı

### 1. Veri Ön İşleme
- **BAF Veri Seti Dosyası:** https://drive.google.com/file/d/1hGVjDl1daPL3HHH-S9pmNTJ0ppPKdQso/view?usp=sharing
- **Veri Yükleme:** BAF veri seti `base.csv` dosyasından yüklenir.
- **Kategorik Verilerin Dönüşümü:** Kategorik değişkenler `OneHotEncoder` ile dönüştürülür.
- **Veri Ölçeklendirme:** Sürekli değişkenler `MinMaxScaler` ile ölçeklendirilir.
- **Binary Verilerin Düzeltilmesi:** İkili değişkenler 0 ve 1 değerlerine dönüştürülür.

### 2. GAN Mimarisi
- **Generator:** Rastgele latent vektör alıp, sahte veri örnekleri üretir.
- **Discriminator:** Gerçek ve sahte veri örneklerini ayırt etmeye çalışır.
  
### 3. Eğitim Süreci
- **Kayıplar:** Discriminator ve Generator kayıpları `BCELoss` fonksiyonu ile hesaplanır.
- **Optimizasyon:** Adam optimizasyon algoritması kullanılır.
- **Eğitim:** Eğitim süresi ve kayıplar her epoch'ta raporlanır.

### 4. Modellerin Kaydedilmesi
- Eğitim tamamlandıktan sonra Generator ve Discriminator modelleri `Pickle` ile kaydedilir.

### 5. Yapay Veri Üretimi
- **Veri Üretimi:** Kayıtlı Generator modeli ile sahte veri üretilir.
- **Ölçeklendirme:** Üretilen sayısal veriler ters ölçeklendirilir.
- **Sonuç Karşılaştırma:** Gerçek ve yapay veriler histogramlar aracılığıyla karşılaştırılır.
- **Yapay Veri Dosyası:** https://drive.google.com/file/d/1Oi6PujIDjLgkYunO19nKZScd5nQSsqwc/view?usp=sharing

## Kullanılan Kütüphaneler

- `torch`
- `pandas`
- `scikit-learn`
- `matplotlib`
- `pickle`

## Kullanım

Proje gereksinimlerini yüklemek için aşağıdaki komutu çalıştırın:
```bash
pip install -r requirements.txt

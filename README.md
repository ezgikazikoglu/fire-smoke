#  Yangın ve Duman Tespit Projesi

Bilgisayar mühendisliği kapsamında geliştirilen bu proje, görüntü işleme ve derin öğrenme tekniklerini kullanarak görseller üzerinde **yangın** ve **duman** tespiti yapmayı amaçlamaktadır.

Projede klasik görüntü işleme yöntemleri ile derin öğrenme modeli birlikte kullanılmıştır. Sistem; veri ön işleme, veri zenginleştirme (augmentation), yangın/duman analizi ve sınıflandırma adımlarını içermektedir.

---

#  Proje Özeti

Bu projede:

*  HSV renk uzayı ile yangın analizi
*  YCbCr renk uzayı ile duman analizi
*  ResNet50 tabanlı derin öğrenme modeli
*  Veri zenginleştirme (augmentation)
*  Confusion Matrix ve performans analizi
*  Tek görsel üzerinden tahmin sistemi
*  Gelişmiş görüntü ön işleme teknikleri
*  Texture (LBP) analizi

uygulanmıştır.

---

#  Kullanılan Teknolojiler

* Python
* OpenCV
* PyTorch
* Torchvision
* NumPy
* Matplotlib
* PIL (Pillow)
* Scikit-learn
* Seaborn

---

#  Proje Yapısı

```bash
fire_project/
│
├── FIRE-SMOKE-DATASET/
│   ├── train/
│   └── test/
│
├── AugmentedDataset/
│   ├── train/
│   └── test/
│
├── fireSmokeProject_SONv.ipynb
└── README.md
```

---

#  Kullanılan Yöntemler

## 1️⃣ Yangın Tespiti (HSV)

Yangın tespiti için HSV renk uzayı kullanılmıştır.
Yangın genellikle kırmızı, turuncu ve sarı tonlarında olduğu için bu renk aralıkları filtrelenmiştir.

### Avantajları

* Renk tabanlı hızlı analiz
* Gerçek zamanlı çalışmaya uygun yapı
* Yangın bölgelerini maskeleme imkanı

---

## 2️⃣ Duman Tespiti (YCbCr)

Duman analizi için YCbCr renk uzayı kullanılmıştır.
Dumanın düşük doygunluklu gri tonlara sahip olması analizde temel kriter olarak değerlendirilmiştir.

### Avantajları

* Gri tonları daha başarılı ayırma
* Düşük ışıkta daha stabil sonuçlar
* Arka plandan bağımsız analiz

---

## 3️⃣ Texture Analizi (LBP)

LBP (Local Binary Pattern) yöntemi ile görüntü dokuları analiz edilmiştir.
Yangın ve dumanın karakteristik doku yapılarından faydalanılmıştır.

---

## 4️⃣ Veri Zenginleştirme (Augmentation)

Model performansını artırmak için veri setine farklı dönüşümler uygulanmıştır:

* Rastgele döndürme
* Yatay çevirme
* Gürültü ekleme
* Görüntü varyasyonları

Bu sayede modelin farklı senaryolarda daha başarılı sonuç vermesi hedeflenmiştir.

---

#  Derin Öğrenme Modeli

Projede transfer learning yaklaşımı ile **ResNet50** modeli kullanılmıştır.

### Model Özellikleri

* Önceden eğitilmiş (pretrained) ResNet50
* Son katman proje sınıflarına göre yeniden düzenlenmiştir
* GPU desteği bulunmaktadır
* PyTorch framework kullanılmıştır

### Sınıflar

* Fire
* Smoke
* Neutral

---

#  Kurulum

## 1. Projeyi Klonlayın

```bash
git clone https://github.com/kullaniciadi/fire-smoke-detection.git
cd fire-smoke-detection
```

---

## 2. Gerekli Kütüphaneleri Kurun

```bash
pip install torch torchvision opencv-python numpy matplotlib pillow scikit-learn seaborn
```

---

#  Çalıştırma

Jupyter Notebook üzerinden çalıştırabilirsiniz:

```bash
jupyter notebook
```

Ardından:

```bash
fireSmokeProject_SONv.ipynb
```

notebook dosyasını açın.

---

#  Model Eğitimi

Model eğitimi aşağıdaki adımları içerir:

1. Dataset yükleme
2. Augmentation işlemleri
3. DataLoader oluşturma
4. ResNet50 eğitimi
5. Test doğruluğu hesaplama
6. Confusion Matrix oluşturma

---

#  Tek Görsel Tahmini

Sistem tek bir görsel üzerinde:

* Yangın analizi
* Duman analizi
* Model tahmini
* Olasılık hesaplama

işlemlerini gerçekleştirebilir.

Örnek kullanım:

```python
predict_image("test.jpg")
```

---

#  Performans Analizi

Projede model performansını değerlendirmek için:

* Accuracy
* Classification Report
* Confusion Matrix

metrikleri kullanılmıştır.

---

#  Projenin Amaçları

Bu projenin temel amaçları:

* Erken yangın tespiti
* Görüntü tabanlı güvenlik sistemleri geliştirmek
* Yapay zeka destekli afet algılama sistemleri oluşturmak
* Derin öğrenme ve görüntü işleme tekniklerini birlikte kullanmak

---

#  Gelecekte Yapılabilecek Geliştirmeler

*  Gerçek zamanlı kamera desteği
*  Mobil uygulama entegrasyonu
*  Bulut tabanlı analiz sistemi
*  Alarm sistemi entegrasyonu
*  Video akışı üzerinden canlı analiz
* YOLO tabanlı nesne tespiti entegrasyonu

---

#  Geliştirici

Bu proje bilgisayar mühendisliği görüntü işleme dersi kapsamında geliştirilmiştir.

---

#  Lisans

Bu proje eğitim amaçlı geliştirilmiştir.

# Akbank Derin Öğrenme Bootcamp Projesi: Maymun Türleri Sınıflandırması

Bu proje, Akbank Derin Öğrenme Bootcamp'i kapsamında gerçekleştirilmiştir. Proje, evrişimli sinir ağları (CNN) kullanarak 10 farklı maymun türünün görüntüler üzerinden sınıflandırılmasını amaçlamaktadır.

## 1. Projenin Amacı

Bu projenin temel amacı, bir derin öğrenme projesinin tüm adımlarını (veri ön işleme, model oluşturma, eğitim, değerlendirme ve optimizasyon) pratik olarak uygulamaktır. Görüntü sınıflandırma problemi üzerinden CNN mimarilerinin ve özellikle Transfer Learning tekniğinin etkinliğini deneyimlemek hedeflenmiştir.

## 2. Veri Seti

Projede Kaggle üzerinde bulunan "10 Monkey Species" veri seti kullanılmıştır.

* **Veri Seti Linki:** [https://www.kaggle.com/datasets/slothkong/10-monkey-species](https://www.kaggle.com/datasets/slothkong/10-monkey-species)
* **İçerik:** Veri seti, 10 farklı maymun türüne ait yaklaşık 1400 adet eğitim ve doğrulama görüntüsü içermektedir.
* **Sınıflar:** `n0`'dan `n9`'a kadar etiketlenmiş 10 sınıf bulunmaktadır.

## 3. Kullanılan Yöntemler

Projede yüksek başarı oranına ulaşmak için **Transfer Learning** tekniği ana strateji olarak benimsenmiştir.

* **Model Mimarisi:** Temel model olarak ImageNet üzerinde eğitilmiş **EfficientNetB0** kullanılmıştır. Bu modelin üzerine `GlobalAveragePooling2D`, `Dense` ve `Dropout` katmanlarından oluşan özel bir sınıflandırıcı eklenmiştir.
* **Veri Ön İşleme:** Görüntüler `ImageDataGenerator` ile modele beslenmiş, eğitim setine **Data Augmentation** (döndürme, yakınlaştırma vb.) uygulanarak modelin genelleme yeteneği artırılmıştır.
* **Optimizasyon:** Model, düşük bir öğrenme oranına (`0.0001`) sahip `Adam` optimize edici ile eğitilmiştir.

## 4. Elde Edilen Sonuçlar

Yapılan eğitim sonucunda, Transfer Learning yaklaşımının ne kadar etkili olduğu görülmüştür. Doğrulama (validation) seti üzerinde **~%97** gibi oldukça yüksek bir sınıflandırma doğruluğuna ulaşılmıştır. Detaylı performans metrikleri (`Classification Report`, `Confusion Matrix`) ve modelin öğrenme eğrileri (`Accuracy/Loss` grafikleri) Kaggle notebook'unda sunulmuştur.

## 5. Kaggle Notebook Linki

Projenin tüm kodları, Markdown açıklamaları ve çıktıları aşağıdaki Kaggle notebook'unda bulunmaktadır:

**[https://www.kaggle.com/code/sarkazimabi/monkey-species](https://www.kaggle.com/code/sarkazimabi/monkey-species)**

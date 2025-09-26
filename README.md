# CNN ile Görüntü Sınıflandırma Projesi  

Bu proje kapsamında **Intel Image Classification** veri seti üzerinde bir **Convolutional Neural Network (CNN)** modeli geliştirilmiştir.  
Amaç, derin öğrenme yöntemlerini kullanarak görselleri doğru sınıflara ayırmak, farklı hiperparametre ayarlarını denemek ve sonuçları karşılaştırarak **en iyi modeli seçmektir**.  

---

## Projenin Amacı  
- Görüntü sınıflandırma probleminde CNN mimarisini uygulamak  
- **Veri ön işleme + Data Augmentation** yöntemleri ile daha sağlam bir model kurmak  
- Farklı **optimizer**, **learning rate** ve **dropout** değerleriyle deneyler yapmak  
- **Eğitim / Doğrulama / Test** süreçlerini analiz edip sonuçları görselleştirmek  
- En iyi modeli seçip **Grad-CAM** tekniği ile kararlarını yorumlamak  

---

## Veri Seti Hakkında  
- Veri seti: **Intel Image Classification Dataset**  
- Görseller 6 farklı sınıfa ayrılmıştır:  
  - Doğal Manzara  
  - Şehir  
  - Dağ  
  - Deniz  
  - Bina  
  - Orman  
- Görseller yeniden boyutlandırılarak **128x128 piksel** formatına getirilmiştir.  
- **Train / Validation / Test** olmak üzere 3 parçaya ayrılmıştır.  

---

## Kullanılan Yöntemler  
- **CNN Mimarisi**: Conv2D + MaxPooling + Dropout + Dense (ReLU & Softmax)  
- **Data Augmentation**: Flip, Rotation, Zoom, Translation, Contrast, Brightness  
- **Optimizer Denemeleri**: `Adam`, `RMSprop`, `SGD`  
- **EarlyStopping** ile aşırı öğrenmeyi (overfitting) engelleme  
- **Eğitim grafikleri**: Accuracy ve Loss görselleştirmeleri  
- **Grad-CAM**: Modelin hangi piksellere odaklandığını görselleştirme  

---

## Deneyler ve Metrikler  

Dört farklı konfigürasyon test edilmiştir (**Deneme 1 / 2 / 3 / 4**):  
1. **Deneme 1** → Basit CNN + Adam optimizer  
2. **Deneme 2** → Daha derin CNN (3 Conv blok) + Adam optimizer  
3. **Deneme 3** → CNN + RMSprop optimizer + Dropout 0.5  
4. **Deneme 4** → CNN + SGD optimizer + farklı batch size  

Sonuçların karşılaştırması grafiklerle yapılmış, **Validation Accuracy & Validation Loss** eğrileri aynı grafikte gösterilmiştir.  

 Elde edilen sonuçlardan en iyi performansı **Deneme 2** göstermiştir:  
- **Test Accuracy** ≈ %80.70  
- Confusion Matrix ve Classification Report ile detaylı analiz yapılmıştır.  

---

## Sonuç ve Yorumlar  
- **Data Augmentation** modeli daha genelleştirilebilir hale getirmiştir.  
- **Dropout** kullanımı aşırı öğrenmeyi azaltmıştır.  
- Farklı optimizer denemeleri, modelin eğitimi üzerinde ciddi etki göstermiştir.  
- En başarılı model üzerinde **Grad-CAM** ile görsel yorumlama yapılmış ve modelin hangi bölgelere odaklandığı analiz edilmiştir.  

---

## Gelecek Çalışmalar  
- Daha derin CNN mimarileri (ResNet, EfficientNet vb.) denenebilir.  
- Transfer Learning kullanılarak önceden eğitilmiş modellerden faydalanılabilir.  
- Daha yüksek çözünürlüklü görseller üzerinde eğitim yapılabilir.  
- Hyperparameter tuning (GridSearch / Optuna) ile daha iyi sonuçlar alınabilir.  

---

##  Kaggle Notebook Linki  
https://www.kaggle.com/code/bahalor1/bahalor-derinogrenmeyegiris

---

# EuroSAT-CNN-VGG16


EuroSAT-CNN-VGG16 

EuroSAT Arazi Kullanımı Sınıflandırması (Deep Learning) 

Bu proje, EuroSAT (RGB) veri setini kullanarak uydu görüntülerini 10 farklı arazi sınıfına (Orman, Nehir, Otoyol, Endüstriyel Alan vb.) ayıran bir Derin Öğrenme uygulamasıdır. 


Projede Transfer Learning etkinliğini ölçmek için iki farklı yaklaşım karşılaştırılmıştır: 
Custom CNN Mimarisi (Sıfırdan Tasarım) 
VGG16 ile Transfer Learning (ImageNet Ağırlıklarıyla) 

Sonuçlar ve Analiz 
Genel beklentinin aksine, bu veri setinde sıfırdan tasarlanan hafif CNN modeli, devasa VGG16 modelinden daha yüksek performans göstermiştir. 

Custom CNN 
3-Blok ConvNet + Dropout 

~93% acc

~91% val_acc

VGG16 
Transfer Learning (Dondurulmuş) 

~90% acc

~88% val_acc


VGG16 Neden Geride Kaldı? 
Alan Uyuşmazlığı (Domain Mismatch): VGG16, doğal nesneler (kedi, araba vb.) üzerinde eğitilmiştir ve şekil/kenar tespiti odaklıdır. Uydu görüntüleri ise daha çok doku (texture) ve spektral özelliklere dayanır. 
Çözünürlük: VGG16 yüksek çözünürlüklü (224x224) görseller için optimize edilmiştir. $64 \times 64$ boyutundaki EuroSAT verilerinde derin katmanlar mekansal bilgi kaybına yol açmıştır. 

Teknolojiler 
Python & TensorFlow / Keras 
TensorFlow Datasets (TFDS) (Data Pipeline Optimizasyonu için) 
Matplotlib (Görselleştirme) 

 

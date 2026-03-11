DL Background ve Autoencoder Ödevi: Siber Güvenlik Uygulamaları
Bu proje, derin öğrenme (Deep Learning) temelleri ve Autoencoder mimarileri kullanılarak ağ tabanlı bir Saldırı Tespit Sistemi (IDS) geliştirilmesini konu alan iki aşamalı bir çalışmadır. Proje kapsamında siber saldırıları tespit etmek için hem denetimli (supervised) hem de denetimsiz (unsupervised) yaklaşımlar NSL-KDD veri seti üzerinde test edilmiştir.

🛡️ Proje 1: Derin Öğrenme Tabanlı Sınıflandırma (CNN & AE-CNN)
Bu aşamada, ağ trafiğini "Normal" veya "Saldırı" olarak sınıflandırmak için iki farklı mimari karşılaştırılmıştır:

Standart CNN: 119 öznitelikten oluşan ham veriyi doğrudan işleyen 1 boyutlu evrişimli sinir ağı.

AE-CNN (Hibrit): Bir Autoencoder modelinin Encoder kısmı özellik çıkarıcı olarak kullanılmıştır. Veri, 119 boyuttan 32 boyutlu bir gizli uzaya (latent space) sıkıştırılarak CNN sınıflandırıcıya beslenmiştir.

Öne Çıkan Bulgular
Aşırı Öğrenme Kontrolü: Eğitim ve doğrulama grafiklerinin paralelliği, modellerin veriyi ezberlemediğini (overfitting olmadığını) kanıtlamıştır.

Boyut İndirgeme: Autoencoder kullanımı sayesinde veri boyutu ciddi oranda düşürülmesine rağmen, saldırı yakalama başarısının (Recall) arttığı gözlemlenmiştir.

🔍 Proje 2: VAE ile Anomali Tespiti (Anomalous Traffic Detection)
İkinci aşamada, saldırıların türünü bilmeye gerek duymayan, sadece "normal" davranışı öğrenen Variational Autoencoder (VAE) mimarisi kullanılmıştır:

Çalışma Mantığı: Model sadece normal ağ trafiği ile eğitilerek sistemin "normal" imzasını bir olasılık dağılımı olarak öğrenmiştir.

Anomali Tespiti: Test verisi üzerindeki yüksek rekonstrüksiyon hatası (reconstruction error), sistemin normalden saptığını ve bir anomali (saldırı) olduğunu işaret etmektedir.

Performans Sonuçları
ROC-AUC Score: 0.94 (Yüksek ayırt edicilik gücü).

Precision: 0.92 (Düşük yanlış alarm oranı).

Eşik Değeri (Threshold): Eğitim verisinin hata dağılımının %95 persentili kullanılarak belirlenmiştir.

🛠️ Kullanılan Teknolojiler
Frameworkler: PyTorch, TensorFlow / Keras.

Veri Seti: NSL-KDD.

Kütüphaneler: NumPy, Pandas, Scikit-learn, Matplotlib, Seaborn.

📁 Repo Yapısı
/Homework-1/: CNN ve AE-CNN kodları, grafikler ve metrik analizleri.

/Homework-2/: VAE anomali tespiti, hata dağılım histogramı ve ROC eğrisi.

/data/: Veri seti yükleme talimatları.

Geliştiriciler:
Şevval Ayça Çerence - 152120211128

Emre Alaybeyoğlu - 152120211160

# Denoising_Autoencoder

Gauss ve tuz-biber gürültüsü içeren görüntülerin iyileştirilmesi için geliştirilmiştir.

## Veri Setleri

CelebA ve Google Landmarks Dataset v2 veri setleri ile eğitim yapılmıştır.
CelebA veri seti aşağıdaki link verilen adreslerden indirilebilir.

    https://mmlab.ie.cuhk.edu.hk/projects/CelebA.html

Google Landmarks Dataset v2 veri seti aşağıda verilen sayfada anlatılmıştır. Burada verilen indirme linki ile indirilebilir.

   https://github.com/cvdfoundation/google-landmark
   
indirme link:  https://s3.amazonaws.com/google-landmark/train/images_000.tar

## Model Parametreleri

batch_size : 10 seçilmiştir. Veriler farklı batch'lere ayrılarak GPU ile verilerin daha hızlı eğitilmesini sağlar.

input_shape : 256x256 seçilmiştir. Görüntülerin model eğitilmeden boyutları aynı değere çekilir.

GaussNoise: Görüntülere gauss gürültüsü eklenmesi için kullanılan fonksiyon

SaltandPaperNoise: Görüntülere tuz-biber gürültüsü eklenmesi için kullanılan fonksiyon

## Model Kullanımı

Veri seti indirildikten sonra "dataset_path" değişkenine verilerin bulunduğu dosya yolu gönderilir.
Kullanılacak olan gauss ve tuz-biber gürültüleri için "GaussNoise" veya "SaltandPaperNoise" fonksiyonları seçilerek görüntülere gürültü eklenir.
Model eğitimi yapıldığında "my_model.h5" dosyasına model ağırlıkları kaydedilmektedir. 
Model tekrar kullanılmak istenirse "tf.keras.models.load_model('my_model.h5')" komutu kullanılarak yüklenebilir.

# Göktuğ Face Recognition System

Python ve InsightFace kullanılarak geliştirilmiş yüz tanıma sistemi.

## Proje Hakkında

Bu proje, önceden eğitilmiş InsightFace modeli kullanarak yüz görüntülerinden özellik vektörleri (embedding) oluşturur ve test görüntülerindeki yüzleri referans yüz profiliyle karşılaştırır.

Karşılaştırma işlemi **cosine similarity** yöntemi kullanılarak gerçekleştirilir.

## Kullanılan Teknolojiler

- Python
- InsightFace
- OpenCV
- NumPy
- Pandas
- Google Colab

## Sistem Nasıl Çalışıyor?

1. InsightFace yüz tanıma modeli yüklenir.
2. Referans görüntülerindeki yüzler tespit edilir.
3. Referans yüzlerden 512 boyutlu embedding'ler oluşturulur.
4. Embedding'lerin ortalaması alınarak yüz profili oluşturulur.
5. Test görüntülerindeki yüzler analiz edilir.
6. Test embedding'i ile referans profil arasındaki cosine similarity hesaplanır.
7. Belirlenen threshold değerine göre yüzün tanınıp tanınmadığı belirlenir.
8. Sonuçlar tablo halinde gösterilir.
9. Sistem test doğruluk oranını hesaplar.

## Test Sonuçları

Projede 4 adet Göktuğ fotoğrafı ve 4 adet farklı kişiye ait fotoğraf test edilmiştir.

| Test Grubu | Fotoğraf Sayısı | Doğru Sonuç |
|---|---:|---:|
| Göktuğ | 4 | 4/4 |
| Farklı kişi | 4 | 4/4 |
| **Toplam** | **8** | **8/8** |

Bu test setinde elde edilen doğruluk oranı **%100** olmuştur.

> Bu sonuç yalnızca kullanılan küçük test veri setini temsil etmektedir. Daha büyük ve farklı koşullardaki veri setleriyle daha kapsamlı değerlendirme yapılması gerekir.

## Threshold

Bu projede kullanılan başlangıç threshold değeri:

```text
0.50
```

Cosine similarity değeri 0.50 veya üzerindeyse yüz Göktuğ olarak kabul edilir. Daha düşük değerler tanınmayan kişi olarak değerlendirilir.

Threshold değeri farklı veri setleri üzerinde yapılacak testlerle yeniden ayarlanabilir.

## Gizlilik

Yüz görüntüleri kişisel ve biyometrik veri niteliğinde olduğundan test fotoğrafları bu repository içerisinde paylaşılmamıştır.

Repository yalnızca proje kodunu, notebook'u ve dokümantasyonu içerir.

## Proje Dosyası

Ana çalışma:

`face_recognition.ipynb`

Notebook Google Colab üzerinde çalıştırılabilir.

## Geliştirme Alanları

- Daha büyük test veri setleriyle değerlendirme
- Farklı ışık ve açı koşullarında test
- Birden fazla kişinin tanınabilmesi
- Gerçek zamanlı kamera üzerinden yüz tanıma
- Daha kapsamlı performans değerlendirmesi
- Threshold değerinin veri setine göre optimize edilmesi
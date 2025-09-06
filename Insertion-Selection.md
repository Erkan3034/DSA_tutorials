## Sıralama Algoritmaları Projesi
Bu README dosyasında, sıralama algoritmaları üzerine yaptığım bir çalışmayı belgeliyorum. Insertion Sort ve Selection Sort algoritmalarını ele alıp, belirli diziler üzerindeki adımlarını ve performans özelliklerini inceledim.
### Insertion Sort (Araya Ekleme)
Bu bölümde, [22, 27, 16, 2, 18, 6] dizisini Insertion Sort algoritması kullanarak adım adım sıraladım.
1.1. İncelenen Dizi
[22, 27, 16, 2, 18, 6]

1.2. Sıralama Adımları
Bu algoritmanın temel mantığı, dizinin sol tarafında sıralı bir bölüm oluşturmak ve her yeni elemanı bu sıralı bölüme doğru yerine yerleştirmektir. Adımlar şu şekilde gerçekleşti:
 * Başlangıç: İlk elemanı (22) sıralı kabul ettim.
   [ **22** | 27, 16, 2, 18, 6 ]

 * Adım 1: 27'yi ele aldım. 22'den büyük olduğu için yerini korudu.
   [ **22, 27** | 16, 2, 18, 6 ]

 * Adım 2: 16'yı aldım ve sıralı kısımdaki elemanlarla karşılaştırarak en başa yerleştirdim.
   [ **16, 22, 27** | 2, 18, 6 ]

 * Adım 3: 2'yi aldım ve aynı şekilde sıralı kısımdaki doğru yeri olan en başa yerleştirdim.
   [ **2, 16, 22, 27** | 18, 6 ]

 * Adım 4: 18'i aldım. 16'dan büyük, 22'den küçük olduğu için araya yerleştirdim.
   [ **2, 16, 18, 22, 27** | 6 ]

 * Adım 5: Son olarak 6'yı aldım ve 2 ile 16 arasına yerleştirerek sıralamayı tamamladım.
   [ **2, 6, 16, 18, 22, 27** ]

1.3. Big-O Analizi
Algoritmanın performansı üzerine yaptığım teorik analiz:
 * En Kötü Durum (Worst Case): O(n^2)
 * Ortalama Durum (Average Case): O(n^2)
 * En İyi Durum (Best Case): O(n) (Dizi zaten sıralıysa)
Genel kabul, en kötü durum senaryosu olan O(n^2)'dir.

1.4. Arama Durumu (Time Complexity) Analizi
Sıralamayı tamamladıktan sonra elde ettiğim dizi:
[2, 6, 16, 18, 22, 27]
Bu dizide 18 sayısını arama senaryosunu, problemde verilen tanımlara göre inceledim:
 * Best case: Dizinin başındaki eleman.
 * Worst case: Dizinin sonundaki eleman.
 * Average case: Dizinin ortasındaki eleman.
18 sayısı dizinin ortasında bulunduğundan, bu arama işlemi Average Case kapsamına girer.


### Selection Sort (Seçmeli Sıralama)
Bu bölümde, [7, 3, 5, 8, 2, 9, 4, 15, 6] dizisine Selection Sort algoritmasını uyguladım ve ilk 4 adımı kaydettim. Bu yöntemde, her adımda sıralanmamış kısımdaki en küçük elemanı bulup bu kısmın başına taşıdım.
2.1. İncelenen Dizi
[7, 3, 5, 8, 2, 9, 4, 15, 6]

2.2. İlk 4 Adım
 * Adım 1: Tüm dizideki en küçük eleman olan 2'yi buldum ve en baştaki 7 ile yerini değiştirdim.
   [ **2** | 3, 5, 8, 7, 9, 4, 15, 6 ]

 * Adım 2: Kalan kısımda en küçük eleman 3'tü. Zaten doğru yerde olduğu için bir değişiklik yapmadım.
   [ **2, 3** | 5, 8, 7, 9, 4, 15, 6 ]

 * Adım 3: Kalan kısımdaki en küçük eleman 4'ü buldum ve bu bölümün başındaki 5 ile yerini değiştirdim.
   [ **2, 3, 4** | 8, 7, 9, 5, 15, 6 ]

 * Adım 4: Son olarak, kalan kısımdaki en küçük eleman olan 5'i buldum ve bölümün başındaki 8 ile değiştirdim.
   [ **2, 3, 4, 5** | 7, 9, 8, 15, 6 ]


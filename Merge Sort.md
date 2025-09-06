## Merge Sort:
Merge Sort, bir "böl ve yönet" (divide and conquer) algoritmasıdır. Bu yaklaşım, bir diziyi tek elemanlı alt diziler kalana kadar sürekli olarak ikiye bölme prensibine dayanır. Ardından, bu tek elemanlı alt diziler birleştirilerek ve sıralanarak orijinal dizi sıralı bir hale getirilir.
Merge Sort Aşamaları: [16, 21, 11, 8, 12, 22]

Aşağıda, verilen dizinin Merge Sort algoritmasıyla sıralanma aşamaları adım adım gösterilmiştir.
### 1. Bölme Aşaması (Divide)
Dizi, tek elemanlı alt diziler elde edilene kadar sürekli olarak ikiye bölünür:
 * [16, 21, 11, 8, 12, 22]
 * [16, 21, 11] ve [8, 12, 22]
 * [16, 21] ve [11] ve [8, 12] ve [22]
 * [16] ve [21] ve [11] ve [8] ve [12] ve [22]
### 2. Birleştirme ve Sıralama Aşaması (Merge & Sort)
Şimdi, tek elemanlı alt diziler birleştirilerek ve sıralanarak orijinal dizinin sıralı hali oluşturulur.
 * [16] ve [21] birleşir: [16, 21]
 * [11] zaten sıralı
 * [8] ve [12] birleşir: [8, 12]
 * [22] zaten sıralı
 * [16, 21] ve [11] birleşir: [11, 16, 21]
 * [8, 12] ve [22] birleşir: [8, 12, 22]
 * [11, 16, 21] ve [8, 12, 22] birleşir: [8, 11, 12, 16, 21, 22]
## Big-O Gösterimi
Merge Sort algoritmasının zaman karmaşıklığı O(n \log n)'dir. Bu karmaşıklık, en iyi, ortalama ve en kötü durum senaryolarında aynıdır çünkü algoritma her zaman diziyi ikiye böler ve birleştirir.
 * Bölme aşaması: Diziyi her seferinde ikiye böldüğü için \log n karmaşıklığına sahiptir.
 * Birleştirme aşaması: Her birleştirme adımında, tüm elemanların üzerinden geçildiği için n karmaşıklığına sahiptir.
Bu iki aşamanın birleşimi, genel zaman karmaşıklığını O(n \log n) yapar.

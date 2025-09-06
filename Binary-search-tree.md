# Binary Search Tree Projesi (Proje 3)
---
Merhaba, bu projede verilen diziyi kullanarak Binary Search Tree (BST) yapısını oluşturdum.  
Dizimiz şu şekilde:

[7, 5, 1, 8, 3, 6, 0, 9, 4, 2]

---

##  Binary Search Tree Nedir?

Binary Search Tree (BST), verileri düzenli bir şekilde saklamamızı sağlayan özel bir ağaç yapısıdır.  
Kuralları basit:  
- Her düğümün **en fazla 2 alt düğümü** olur.  
- **Sol alt ağaç**: düğümden küçük değerleri tutar.  
- **Sağ alt ağaç**: düğümden büyük değerleri tutar.  

Bu kurallar sayesinde arama, ekleme, silme işlemleri hızlı yapılır (ortalama O(log n)).  

---

##  Adım Adım Yerleştirme

- İlk eleman **7** → **root 7’dir**.  
- **5**, 7’den küçük → root’un **soluna**.  
- **1**, 7’den küçük → 5’ten küçük → **5’in soluna**.  
- **8**, 7’den büyük → root’un **sağına**.  
- **3**, 7’den küçük → 5’ten küçük → 1’den büyük → **1’in sağına**.  
- **6**, 7’den küçük → 5’ten büyük → **5’in sağına**.  
- **0**, 7’den küçük → 5’ten küçük → 1’den küçük → **1’in soluna**.  
- **9**, 7’den büyük → 8’den büyük → **8’in sağına**.  
- **4**, 7’den küçük → 5’ten küçük → 1’den büyük → 3’ten büyük → **3’ün sağına**.  
- **2**, 7’den küçük → 5’ten küçük → 1’den büyük → 3’ten küçük → **3’ün soluna**.  

---

##  Ortaya Çıkan Ağaç

7
    /   \
   5     8
  / \      \
 1   6      9
/ \

0   3 / 
2   4

---

##  Görselleştirilmiş Hali

Ağacı matplotlib ve networkx kütüphaneleriyle çizdirdim:  

```python
import matplotlib.pyplot as plt
import networkx as nx

# BST bağlantıları
edges = [
    (7, 5), (7, 8),
    (5, 1), (5, 6),
    (8, 9),
    (1, 0), (1, 3),
    (3, 2), (3, 4)
]

G = nx.DiGraph()
G.add_edges_from(edges)

pos = {
    7: (0, 4),
    5: (-2, 3), 8: (2, 3),
    1: (-3, 2), 6: (-1, 2), 9: (3, 2),
    0: (-3.5, 1), 3: (-2.5, 1),
    2: (-3, 0), 4: (-2, 0)
}

plt.figure(figsize=(8,6))
nx.draw(G, pos, with_labels=True, arrows=False, node_size=1500,
        node_color="lightblue", font_size=10, font_weight="bold")
plt.title("Binary Search Tree", fontsize=14)
plt.show()


---

 BST Insert Kodum

Aşağıda kendi insert fonksiyonumla verilen diziyi BST’ye yerleştirdim:

class Node:
    def __init__(self, key):
        self.key = key
        self.left = None
        self.right = None

class BST:
    def __init__(self):
        self.root = None

    def insert(self, key):
        if self.root is None:
            self.root = Node(key)
        else:
            self._insert(self.root, key)

    def _insert(self, root, key):
        if key < root.key:
            if root.left is None:
                root.left = Node(key)
            else:
                self._insert(root.left, key)
        else:
            if root.right is None:
                root.right = Node(key)
            else:
                self._insert(root.right, key)

    def inorder(self, root):
        if root is not None:
            self.inorder(root.left)
            print(root.key, end=" ")
            self.inorder(root.right)

# Kullanım
tree = BST()
data = [7, 5, 1, 8, 3, 6, 0, 9, 4, 2]

for val in data:
    tree.insert(val)

print("Inorder Traversal: ")
tree.inorder(tree.root)

#Çıktı:

#0 1 2 3 4 5 6 7 8 9

#Yani sıralı bir şekilde çıktı aldım.

### Sonuç

Bu projede:

BST’nin ne olduğunu öğrendim,

Adım adım diziden ağacı çıkardım,

Python koduyla BST’yi oluşturdum,

Görselleştirmeyi matplotlib ile yaptım.


Artık BST mantığını çok daha iyi anlıyorum :)



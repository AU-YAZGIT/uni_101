# Python Atölyesi: YAZGİT Python & Görüntü İşleme 101

Sıfırdan Python öğrenip dört derste kamerayla el hareketlerini algılayan bir uygulamaya ulaştığımız uygulamalı atölye.

---

## 1. Atölye Bilgileri

| | |
|---|---|
| **Atölye** | YAZGİT Python & Görüntü İşleme 101 |
| **Eğitmen** | [@irfanmetekendirci-lang](https://github.com/irfanmetekendirci-lang) |
| **Tarihler** | 12, 14, 19 ve 21 Ekim 2026 (2 hafta, 4 ders) |
| **Kaynak Kod** | [github.com/AU-YAZGIT/python_ve_goruntu_isleme_101](https://github.com/AU-YAZGIT/python_ve_goruntu_isleme_101) |
| **Atölye Sitesi** | [au-yazgit.github.io/python_ve_goruntu_isleme_101](https://au-yazgit.github.io/python_ve_goruntu_isleme_101/) |

> Geçmiş ve yaklaşan diğer etkinlikler için [Etkinlik Arşivi](../etkinlikler/arsiv.md) sayfasına göz atabilirsiniz.

---

## 2. Öğrenme Sırası

Bu rehberde Python'a başlamak için önerdiğimiz yol:

1. **[Python Kurulumu](python-kurulumu.md):** Python'ı, VS Code eklentilerini ve sanal ortamı hazırlayın.
2. **Python Atölyesi (bu sayfa):** Temellerden görüntü işlemeye, dört derslik uygulamalı program.
3. **[Önerilen Kaynaklar](kaynaklar.md):** Atölyeden sonra kendinizi geliştirmeye devam etmek için seçilmiş kaynaklar.

---

## 3. Gereksinimler

* **Python 3.8 veya üzeri** (kurulum için [Python Kurulumu](python-kurulumu.md) sayfasına bakın)
* **VS Code** (kurulum için [VS Code Kurulumu](vscode-kurulumu.md) sayfasına bakın)
* Çalışan bir **web kamerası** (3. ve 4. günler için)

Gerekli kütüphaneleri tek komutla yükleyin (mümkünse bir [sanal ortam](python-kurulumu.md#5-sanal-ortam-venv-olusturma) içinde):

```bash
pip install opencv-python mediapipe numpy
```

Atölye kodlarını bilgisayarınıza almak için:

```bash
git clone https://github.com/AU-YAZGIT/python_ve_goruntu_isleme_101.git
cd python_ve_goruntu_isleme_101
```

---

## 4. Ders Programı

### 1. Gün — 12 Ekim: Python Temelleri

* Temel Python sözdizimi ve veri tipleri
* Listeler ve sözlükler
* Kontrol yapıları: `if`, `for`, `while`
* **Mini uygulama:** Koordinat filtresi

### 2. Gün — 14 Ekim: Fonksiyonlar ve NumPy

* Fonksiyonlar
* NumPy ile çalışma: **görüntü aslında bir matristir**
* Pandas'a kısa bir bakış
* Kurulum kontrolü ve ilk kamera testi

### 3. Gün — 19 Ekim: OpenCV ve El Takibi

* OpenCV ile kamera akışı okuma
* MediaPipe Hands: elin **21 eklem noktası**
* İşaret parmağı ucunu takip etme

### 4. Gün — 21 Ekim: Jest Tanıma ve Bitirme Projesi

* Parmak sayma
* Taş-Kağıt-Makas jest tanıma
* **VisionDraw** bitirme projesi

---

## 5. Bitirme Projesi: VisionDraw

VisionDraw, kameranın önünde parmağınızı hareket ettirerek **havada çizim** yapmanızı sağlayan bir uygulamadır.

| Hareket / Tuş | İşlev |
|---|---|
| Yalnızca **işaret parmağı** açık | **Çizim modu:** Parmak ucunuz kalem gibi çizer. |
| **İşaret + orta parmak** açık | **Gezinme modu:** Çizim yapmadan imleci hareket ettirirsiniz. |
| `C` | Tuvali temizler. |
| `Q` | Uygulamadan çıkar. |

> Projenin kaynak kodu ve adım adım açıklaması [atölye reposunda](https://github.com/AU-YAZGIT/python_ve_goruntu_isleme_101) bulunur.

---

## 6. Isınma: NumPy & OpenCV ile "Merhaba Dünya"

Kurulumun çalıştığını test etmek ve "görüntü = matris" fikrini görmek için aşağıdaki kodu `merhaba.py` adıyla kaydedip `python merhaba.py` ile çalıştırın. Kamera gerekmez.

```python
import cv2
import numpy as np

# 1) Görüntü = matris: 300 satır, 500 sütun, 3 renk kanalı (B, G, R)
#    Her piksel 0-255 arası bir sayı. np.zeros ile tamamen siyah bir tuval elde ederiz.
tuval = np.zeros((300, 500, 3), dtype=np.uint8)
print("Boyut (yükseklik, genişlik, kanal):", tuval.shape)

# 2) NumPy dilimleme ile bir bölgeyi boya: satır 50-150, sütun 50-200 arası mavi.
#    OpenCV renkleri RGB değil BGR sırasıyla tutar: (255, 0, 0) = mavi.
tuval[50:150, 50:200] = (255, 0, 0)

# 3) Aynı işi OpenCV fonksiyonlarıyla yap: yeşil daire ve beyaz yazı.
cv2.circle(tuval, (350, 100), 50, (0, 255, 0), thickness=-1)  # -1 = içi dolu
cv2.putText(tuval, "Merhaba YAZGIT!", (50, 240),
            cv2.FONT_HERSHEY_SIMPLEX, 1.2, (255, 255, 255), 2)

# 4) Tek bir pikseli oku: dairenin merkezi yeşil olmalı.
print("(100, 350) pikseli BGR:", tuval[100, 350])

# 5) Pencerede göster, bir tuşa basılınca kapat.
cv2.imshow("Merhaba Dunya", tuval)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

Ekranda siyah zemin üzerinde mavi bir dikdörtgen, yeşil bir daire ve "Merhaba YAZGIT!" yazısı görmelisiniz. Terminalde ise `(300, 500, 3)` ve `[  0 255   0]` çıktıları yazar.

> **Dikkat:** `cv2.circle` koordinatı `(x, y)` yani (sütun, satır) olarak alır, NumPy dizini ise `[satır, sütun]` şeklindedir. Bu fark 3. günde el eklem noktalarıyla çalışırken önemli olacak.

---

## Sırada Ne Var?

Atölyeyi tamamladıysanız [Önerilen Kaynaklar](kaynaklar.md) sayfasındaki Bilgisayarlı Görü ve Python kaynaklarıyla devam edebilirsiniz.

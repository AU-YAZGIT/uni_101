# Python Kurulumu & VS Code Yapılandırması

Temiz bir Python geliştirme ortamı kurmak ve editör entegrasyonunu sağlamak için gereken adımlar.

---

## 1. Python Kurulumu (Windows)

1. [python.org/downloads](https://www.python.org/downloads/) adresinden güncel Python sürümünü indirin.
2. İndirilen kurulum dosyasını çalıştırın.
3. **KRİTİK ADIM:** Kurulum penceresinin altındaki **`Add python.exe to PATH`** seçeneğini mutlaka işaretleyin. (Bu seçilmezse terminal üzerinden `python` komutu çalışmaz).
4. **"Install Now"** seçeneğiyle kurulumu tamamlayın.
5. Kurulum sonunda ekranda belirirse **"Disable path length limit"** butonuna basarak dosya yolu sınırını kaldırın.

---

## 2. Kurulumu Doğrulama

VS Code içindeki terminali veya komut istemini açıp şu komutları çalıştırın:

```bash
# Python sürümünü kontrol et
python --version

# Paket yöneticisi pip kontrolü
pip --version
```

Ekranda `Python 3.x.x` çıktısını görüyorsanız sistem Python'ı başarıyla tanımıştır.

---

## 3. VS Code Python Eklentileri

VS Code'un sol menüsündeki **Extensions** (`Ctrl + Shift + X`) sekmesinden şu eklentileri yükleyin:

1. **Python (Microsoft):** Kod renklendirme, hata ayıklama (debug) ve temel Python desteği sağlar.
2. **Pylance:** Çok hızlı kod tamamlama (IntelliSense) ve tür denetimi sunar.
3. **Black Formatter:** Python kodlarınızı PEP 8 standartlarına uygun olarak otomatik düzenler.
4. **Jupyter (İsteğe Bağlı):** Veri bilimi ve makine öğrenmesi çalışmaları için `.ipynb` notebook dosyalarını doğrudan editörde çalıştırır.

---

## 4. Python Interpreter (Yorumlayıcı) Seçimi

VS Code'un doğru Python ortamını görmesi için:

1. VS Code içinde `Ctrl + Shift + P` kısayoluyla komut paletini açın.
2. `Python: Select Interpreter` yazıp seçin.
3. Bilgisayarınızda kurulu olan Python sürümünü veya projenize ait `(venv)` ortamını işaretleyin.

---

## 5. Sanal Ortam (venv) Oluşturma

Projelerinizdeki kütüphanelerin birbirini etkilememesi için izole sanal ortam kullanılması önerilir:

```bash
# 1. Ortamı oluştur
python -m venv venv

# 2. Ortamı aktif et (Windows PowerShell)
.\venv\Scripts\Activate.ps1

# Ortamı aktif et (macOS / Linux)
source venv/bin/activate
```
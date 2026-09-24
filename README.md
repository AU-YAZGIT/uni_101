# YAZGİT University 101

**YAZGİT (Yapay Zeka ve Görüntü İşleme Topluluğu)** tarafından Ankara Üniversitesi'ne yeni gelen ve mevcut öğrenciler için hazırlanan, **açık kaynaklı** bir öğrenci ve geliştirici rehberi.
 
🌐 **Site:** [au-yazgit.github.io/uni_101](https://au-yazgit.github.io/uni_101/)

---

## Neler Bulabilirsiniz?
 
- **Topluluk:** YAZGİT nedir, nasıl katılınır, hangi kanallardan iletişim kurulur.
- **Üniversite Hayatı:** Yerleşkeler, kampüs olanakları ve akademik işleyiş.
- **Geliştirici Rehberi:** VS Code ve Python kurulumu, sanal ortam mantığı ve önerilen temel kaynaklar.

> Rehber şu an **iskelet aşamasında**. Sayfaların birçoğu katkıya açıktır. Doldurmak ve zenginleştirmek için topluluk üyelerinin desteğini bekliyoruz!

---

## Katkıda Bulun
 
Bu rehber hepimizin. Kod bilmen gerekmiyor, Markdown yazabilmen yeterli.
 
1. Bir göz at: [Açık Issue'lar](../../issues). Yeni başlıyorsan [`good first issue`](../../labels/good%20first%20issue) etiketli olanlar sana göre.
2. Almak istediğin issue'ya "Bunu ben alıyorum" diye yorum yaz.
3. [CONTRIBUTING.md](CONTRIBUTING.md) dosyasındaki adımları izleyerek yeni bir dal aç, değişikliğini yap ve Pull Request (PR) gönder.

Küçük bir yazım hatası mı gördün? Sayfadaki dosyayı GitHub'da açıp kalem simgesine tıklaman ve doğrudan PR göndermen yeterli.

---

## Yerelde Çalıştırma
 
Siteyi kendi bilgisayarında canlı önizlemek için Python 3 gerekir:
 
```bash
git clone [https://github.com/AU-YAZGIT/uni_101.git](https://github.com/AU-YAZGIT/uni_101.git)
cd uni_101
 
python -m venv .venv
# Windows (PowerShell):
.venv\Scripts\activate
# macOS / Linux:
source .venv/bin/activate

pip install mkdocs-material
 
mkdocs serve
```
 
Ardından tarayıcında `http://127.0.0.1:8000` adresini aç. Dosyaları kaydettikçe sayfa otomatik yenilenir.

---

## Proje Yapısı
 
```text
uni_101/
├── .github/workflows/          # Otomatik yayınlama (GitHub Actions CI/CD)
├── docs/                       # Sitenin tüm dokümantasyon içeriği (Markdown)
│   ├── index.md                # Karşılama ve ana sayfa
│   ├── stylesheets/            # Özel stil ve tema düzenlemeleri (extra.css)
│   ├── topluluk/               # Topluluk tanıtımı ve iletişim kanalları
│   │   ├── yazgit-nedir.md
│   │   └── iletisim.md
│   ├── universite/             # Kampüs yaşamı ve akademik bilgiler
│   │   ├── yerleskeler.md
│   │   └── akademik-takvim.md
│   └── yazilim/                # Geliştirici ortamı kurulumları ve kaynaklar
│       ├── vscode-kurulumu.md
│       ├── python-kurulumu.md
│       └── kaynaklar.md
├── mkdocs.yml                  # Site ayarları, tema yapılandırması ve navigasyon
├── CONTRIBUTING.md             # Katkı rehberi
├── LICENSE                     # MIT Lisansı
└── README.md                   # Proje tanıtım ve başlangıç dosyası
```
 
> *Yeni bir sayfa eklediğinde `mkdocs.yml` içindeki `nav:` bölümüne de bağlamayı unutma.*

---

## Kullanılan Teknolojiler
 
- [MkDocs](https://www.mkdocs.org/) ve [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) temasıyla dokümantasyon üretimi
- [GitHub Actions](https://github.com/features/actions) ve [GitHub Pages](https://pages.github.com/) ile otomatik dağıtım
- [Conventional Commits](https://www.conventionalcommits.org/tr/v1.0.0/) standartlarında commit disiplini

---

## Bize Ulaşın
 
- **Instagram:** [@au_yazgit](https://www.instagram.com/au_yazgit/)
- **GitHub:** [AU-YAZGIT](https://github.com/AU-YAZGIT)
- Sorular ve öneriler için [yeni bir issue açabilirsin](../../issues/new).

---

## Lisans
 
Bu proje [MIT Lisansı](LICENSE) ile korunmaktadır.
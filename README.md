# YAZGİT University 101

**YAZGİT (Yapay Zeka ve Görüntü İşleme Topluluğu)** tarafından Ankara Üniversitesi'ne yeni gelen ve mevcut öğrenciler için hazırlanan, **açık kaynaklı** bir öğrenci ve geliştirici rehberi.
 
🌐 **Site:** [au-yazgit.github.io/uni_101](https://au-yazgit.github.io/uni_101/)

## Neler Bulabilirsiniz?
 
- **Topluluk:** YAZGİT nedir, nasıl katılınır, hangi kanallardan ulaşılır.
- **Üniversite Hayatı:** Yerleşkeler, kampüs olanakları ve akademik işleyiş.
- **Geliştirici Rehberi:** Yazılım ve yapay zekaya ilk adımı atarken gereken araçların kurulumu ve önerilen kaynaklar.
> Rehber şu an **iskelet aşamasında**. Sayfaların birçoğunda henüz içerik yok. Doldurmak için yardımına ihtiyacımız var!

## Katkıda Bulun
 
Bu rehber hepimizin. Kod bilmen gerekmiyor, Markdown yazabilmen yeterli.
 
1. Bir göz at: [açık issue'lar](../../issues). Yeni başlıyorsan [`good first issue`](../../labels/good%20first%20issue) etiketli olanlar sana göre.
2. Almak istediğin issue'ya "Bunu ben alıyorum" diye yorum yaz.
3. [CONTRIBUTING.md](CONTRIBUTING.md) dosyasındaki adımları izleyerek değişikliğini yap ve pull request aç.
Küçük bir yazım hatası mı gördün? Sayfadaki dosyayı GitHub'da açıp kalem simgesine tıklaman ve pull request göndermen yeterli.

## Yerelde Çalıştırma
 
Siteyi kendi bilgisayarında görmek için Python 3 gerekir:
 
```bash
git clone https://github.com/AU-YAZGIT/uni_101.git
cd uni_101
 
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install mkdocs-material
 
mkdocs serve
```
 
Ardından tarayıcında `http://127.0.0.1:8000` adresini aç. Dosyaları kaydettikçe sayfa otomatik yenilenir.

## Proje Yapısı
 
```text
uni_101/
├── .github/workflows/   # Otomatik yayınlama (GitHub Actions)
├── docs/                # Sitenin tüm içeriği (Markdown)
│   ├── index.md
│   ├── topluluk/
│   ├── universite/
│   └── yazilim/
├── mkdocs.yml           # Site ayarları, tema ve menü
├── CONTRIBUTING.md      # Katkı rehberi
└── README.md
```
 
Yeni bir sayfa eklediğinde `mkdocs.yml` içindeki `nav:` bölümüne de eklemeyi unutma.
 
## Kullanılan Teknolojiler
 
- [MkDocs](https://www.mkdocs.org/) ve [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) temasıyla site üretimi
- [GitHub Actions](https://github.com/features/actions) ve [GitHub Pages](https://pages.github.com/) ile yayınlama
- [Conventional Commits](https://www.conventionalcommits.org/tr/v1.0.0/) ile commit mesajları
## Bize Ulaşın
 
- Instagram: [@au_yazgit](https://www.instagram.com/au_yazgit/)
- Sorular ve öneriler için [issue açabilirsin](../../issues/new).
## Lisans
 
Lisans bilgisi için [LICENSE](LICENSE) dosyasına bakın.


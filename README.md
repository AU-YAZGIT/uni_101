# YAZGİT University 101

**Türkçe** | [English](README.en.md)

[![Deploy](https://github.com/AU-YAZGIT/uni_101/actions/workflows/deploy.yml/badge.svg)](https://github.com/AU-YAZGIT/uni_101/actions/workflows/deploy.yml)
[![Check](https://github.com/AU-YAZGIT/uni_101/actions/workflows/check.yml/badge.svg)](https://github.com/AU-YAZGIT/uni_101/actions/workflows/check.yml)

**YAZGİT (Yapay Zeka ve Görüntü İşleme Topluluğu)** tarafından hazırlanan, yeni gelen ve mevcut öğrenciler için açık kaynaklı üniversite ve geliştirici rehberi.

🌐 **Canlı site:** <https://au-yazgit.github.io/uni_101/>

## Nasıl katkı sağlarım?

Bu rehber öğrencilerin katkısıyla büyüyor. Hatalı ya da eksik bir bilgi görürseniz:

1. **Hızlı düzeltme:** Sitede ilgili sayfanın sağ üstündeki düzenle (kalem) simgesine tıklayın, GitHub üzerinde düzenleyip PR açın.
2. **Yeni içerik:** [Açık issue'lara](https://github.com/AU-YAZGIT/uni_101/issues) göz atın. `good first issue` etiketlileri ilk katkı için uygundur.
3. **Kurallar:** PR açmadan önce [katkı rehberini](CONTRIBUTING.md) okuyun. PR başlıkları [Conventional Commits](https://www.conventionalcommits.org/tr/v1.0.0/) biçimindedir (`docs: yerleşkeler sayfasını güncelle`).

## Yerelde çalıştırma

Gereksinim: Python 3.10 veya üstü.

```bash
git clone https://github.com/AU-YAZGIT/uni_101.git
cd uni_101

python -m venv venv
source venv/bin/activate        # Windows PowerShell: .\venv\Scripts\Activate.ps1

pip install -r requirements.txt
mkdocs serve
```

Site `http://127.0.0.1:8000` adresinde açılır ve dosyaları kaydettikçe yenilenir. `main` dalına yapılan her birleştirmeden sonra site GitHub Actions ile otomatik yayınlanır.

PR açmadan önce şu kontrolleri çalıştırın (CI de aynılarını çalıştırır):

```bash
mkdocs build --strict
npx markdownlint-cli2
```

## İletişim

- GitHub: [AU-YAZGIT](https://github.com/AU-YAZGIT)
- Instagram: [@au_yazgit](https://www.instagram.com/au_yazgit/)

## Lisans

Bu proje [LICENSE](LICENSE) dosyasındaki lisans altında yayımlanmıştır.

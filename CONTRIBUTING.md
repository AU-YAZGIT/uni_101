# Katkıda Bulunma Rehberi

YAZGİT University 101'e katkı vermek istediğin için teşekkürler!

Bu repo, Ankara Üniversitesi öğrencileri için hazırlanan açık kaynaklı bir rehber sitesinin kaynağıdır. 

Site [MkDocs Material](https://squidfunk.github.io/mkdocs-material/) ile üretilir ve tüm içerik `docs/` 
klasöründeki Markdown dosyalarından oluşur. Kod bilmen gerekmez, Markdown yazabilmen yeterli.

## İçindekiler

- [Nasıl katkı verebilirim?](#nasıl-katkı-verebilirim)
- [Hızlı yol: tarayıcıdan düzenle](#hızlı-yol-tarayıcıdan-düzenle)
- [Tam yol: fork, clone, branch, PR](#tam-yol-fork-clone-branch-pr)
- [Commit mesajı kuralları](#commit-mesajı-kuralları)
- [İçerik yazım kuralları](#içerik-yazım-kuralları)
- [Pull request sürecinde ne olur?](#pull-request-sürecinde-ne-olur)
- [Davranış kuralları](#davranış-kuralları)

## Nasıl katkı verebilirim?

- **Hata bildir veya düzelt.** Yazım hatası, kırık bağlantı ya da eski bilgi gördüysen issue aç veya doğrudan düzelt.
- **Yeni sayfa öner.** Rehberde olmasını istediğin bir konu varsa issue aç.
- **Tasarım geri bildirimi ver.** Mobil ve karanlık mod görünümünde gördüğün sorunları paylaş.
> Üzerinde çalışmak istediğin bir issue'ya "Bunu ben alıyorum" diye yorum yaz. Böylece aynı işi iki kişi yapmaz.

## Hızlı yol: tarayıcıdan düzenle
 
Küçük düzeltmeler (yazım hatası, bağlantı, tek paragraf) için bilgisayarına hiçbir şey kurmana gerek yok:
 
1. GitHub'da `docs/` altında düzenlemek istediğin `.md` dosyasını aç.
2. Sağ üstteki **kalem simgesine** (Edit this file) tıkla.
3. GitHub senin için otomatik olarak bir fork oluşturur. Değişikliğini yap.
4. **Commit changes...** düğmesine bas, [commit mesajı kurallarına](#commit-mesajı-kuralları) uygun bir mesaj yaz ve **Propose changes** de.
5. Açılan sayfada **Create pull request** düğmesine tıkla.
## Tam yol: fork, clone, branch, PR
 
Yeni sayfa eklemek veya birden fazla dosyayı değiştirmek için bu yolu izle.
 
### 1. Repoyu forkla
 
Repo sayfasının sağ üstündeki **Fork** düğmesine tıkla. Bu, repoyu kendi hesabına kopyalar.
 
### 2. Forkunu bilgisayarına klonla
 
```bash
git clone https://github.com/<kullanici-adin>/uni_101.git
cd uni_101
```
 
İstersen orijinal repoyu da `upstream` olarak ekleyebilirsin, böylece güncel kalırsın:
 
```bash
git remote add upstream https://github.com/AU-YAZGIT/uni_101.git
git fetch upstream
```
 
### 3. Yeni bir branch aç
 
`main` branch'ine **doğrudan commit atma ve push yapma**. Her iş için ayrı bir branch aç:
 
```bash
git switch -c docs/yerleskeler-sayfasi
```
 
Branch adı için önerimiz `tür/kisa-aciklama` biçimidir. Örneğin `docs/iletisim-kanallari`, `fix/kirik-baglanti`, `feat/logo-ekle`.

### 4. Değişikliğini yap
 
Sayfalar `docs/` altındadır:
 
```text
docs/
├── index.md
├── topluluk/
├── universite/
└── yazilim/
```
 
**Yeni sayfa eklersen** dosyayı ilgili klasöre koy ve `mkdocs.yml` içindeki `nav:` bölümüne de ekle, aksi halde menüde görünmez:
 
```yaml
nav:
  - Üniversite Hayatı:
      - Yerleşkeler & Yaşam: universite/yerleskeler.md
      - Yemekhane: universite/yemekhane.md   # yeni sayfa
```
 
### 5. Sitede nasıl göründüğüne bak (isteğe bağlı)
 
Değişikliğini göndermeden önce yerelde önizleyebilirsin. Python 3 gerekir.
 
```bash
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install mkdocs-material
mkdocs serve
```
 
Tarayıcında `http://127.0.0.1:8000` adresini aç. Dosyayı kaydettiğinde sayfa kendiliğinden yenilenir. Karanlık modu ve mobil görünümü de kontrol etmeyi unutma.
 
### 6. Commit at
 
```bash
git add .
git commit -m "docs: yerleşkeler ve yaşam sayfasını doldur"
```
 
### 7. Branch'ini pushla ve PR aç
 
```bash
git push -u origin docs/yerleskeler-sayfasi
```
 
GitHub, repo sayfasında **Compare & pull request** düğmesini gösterecek. Tıkla, başlığı ve açıklamayı doldur. Bir issue'yu çözüyorsan açıklamaya `Closes #12` yaz (12 yerine issue numarası).
PR birleşince issue kendiliğinden kapanır.

## Commit mesajı kuralları
 
Commit mesajlarında [Conventional Commits](https://www.conventionalcommits.org/tr/v1.0.0/) biçimini kullanıyoruz:
 
```text
<tür>: <kısa açıklama>
```
 
| Tür | Ne zaman kullanılır? | Örnek |
|---|---|---|
| `docs` | İçerik veya dokümantasyon ekleme/güncelleme | `docs: iletişim kanallarını ekle` |
| `fix` | Hata, yazım hatası veya kırık bağlantı düzeltme | `fix: akademik takvimdeki tarihi düzelt` |
| `feat` | Siteye yeni özellik ekleme | `feat: son güncelleme tarihini göster` |
| `style` | Biçim değişikliği, içeriği etkilemeyen düzenleme | `style: başlık seviyelerini düzenle` |
| `ci` | GitHub Actions ve otomasyon | `ci: PR'larda build kontrolü ekle` |
| `chore` | Ayarlar ve genel bakım | `chore: mkdocs.yml'e repo_url ekle` |
 
Kısa kurallar:
 
- Açıklama küçük harfle başlasın ve nokta ile bitmesin.
- Ne yaptığını kısaca anlat, "değişiklik yapıldı" gibi belirsiz mesajlar yazma.
- Tek commit'te tek bir konuyu değiştirmeye çalış.
## İçerik yazım kuralları
 
- **Dil:** Türkçe yaz, sade ve anlaşılır bir dil kullan. Sayfaları ilk kez okuyacak birinci sınıf öğrencilerini düşün.
- **Doğruluk:** Tarih, saat, ücret gibi bilgilerin kaynağını ekle (resmî site, duyuru vb.). Emin olmadığın bilgiyi yazma, issue'da sor.
- **Güncellik:** Değişebilecek bilgilerin (takvim, yemekhane fiyatı gibi) yanına geçerli olduğu dönemi yaz.
- **Dosya adları:** Küçük harf, Türkçe karakter ve boşluk olmadan, tire ile yaz. Örnek: `akademik-takvim.md`.
- **Başlıklar:** Her sayfada tek bir `#` başlığı olsun, alt başlıklar `##` ve `###` ile devam etsin.
- **Bağlantılar:** Rehber içi bağlantılarda göreli yol kullan (`../universite/yerleskeler.md`).
- **Kişisel veri:** Telefon numarası, özel e-posta gibi kişisel bilgileri kişinin izni olmadan ekleme.
## Pull request sürecinde ne olur?
 
1. PR'ın bir bakımcı tarafından incelenir. Değişiklik istenirse aynı branch'e yeni commit atman yeterli, PR kendiliğinden güncellenir.
2. Otomatik kontroller (varsa) geçmelidir.
3. Onaylandığında PR `main` branch'ine birleştirilir ve site otomatik olarak yenilenir.
İlk PR'ında takılırsan çekinme, issue'da veya PR'da soru sorabilirsin. Herkes bir yerden başlıyor. :D
 
## Davranış kuralları
 
Bu repoda saygılı, yapıcı ve kapsayıcı olmayı bekliyoruz. Yeni başlayanlara sabırlı ol, geri bildirimi nazikçe ver, kimseyi küçümseme. Uygunsuz davranış gördüğünde bir bakımcıya haber ver.

# IMPOSTER – Türkçe Parti Oyunu

3–12 kişi, tek telefon, tamamen çevrimdışı. Hesap, internet veya kurulum gerekmez.

## Nasıl başlatılır

**En kolay yol:** ZIP dosyasını bir klasöre çıkarın ve `index.html` dosyasına çift tıklayın (Chrome, Edge, Firefox, Safari).

**Telefonda:** Klasörü telefona kopyalayıp `index.html` dosyasını tarayıcıyla açın. Bazı telefonlarda dosya yöneticisi HTML dosyalarını açmaz; bu durumda bilgisayarda yerel sunucu başlatıp aynı Wi‑Fi üzerinden telefondan bağlanabilirsiniz:

```
python3 -m http.server 8000
```

Sonra telefonda `http://BILGISAYAR-IP-ADRESI:8000` adresini açın. (Windows için `baslat.bat`, macOS/Linux için `baslat.sh` dosyaları aynı komutu çalıştırır.)

## Oyun akışı
1. **Yeni Oyun** → oyuncular, imposter sayısı, mod ve kategoriler seçilir.
2. Telefon elden ele geçer: **Kelimeyi Gör** → rolünüzü görün → **Hazırım**.
3. Telefon bir kenara bırakılır. Sırayla sözlü ipucu verilir, tartışılır.
4. Biri **Tartışma Bitti**’ye dokunur. Oylama tamamen **sözlüdür**; uygulama oy tutmaz.
5. **Sonuçları Göster** → roller ve kelimeler açıklanır. Kazananı grup belirler.
6. **Tekrar Oyna** aynı ayarlarla yeni kelime ve yeni rollerle hemen başlar.

## Veröffentlichen (GitHub Pages, Netlify usw.)
Lade den **gesamten Inhalt** des Ordners hoch (nicht den Ordner selbst): `index.html`, `style.css`, `app.js`, `logic.js`, `words.js`, `aciklamalar.js`, `manifest.webmanifest`, die vier `*.png`-Symbole und `.nojekyll`. Das SAMIX-Logo ist als Vektor-SVG **direkt im Code eingebettet** – es braucht keine Bilddatei und keinen Unterordner. Die Ordner `assets/` (Logo-Quelldateien) und `tests/` sind für das Spiel nicht nötig. Bei GitHub: Dateien per „Add file → Upload files“ hochladen, bis alle Dateien in der Liste stehen, dann Seite neu laden (ggf. Cache leeren).

## SAMIX
Logo: `app.js` ve `index.html` içine gömülü vektör SVG (her boyutta keskin, açık/koyu temaya göre renklenir). `assets/` içinde kaynak dosyalar bulunur: `samix-logo.svg`, `samix-logo-dark.svg`, `.png` sürümleri ve `samix-logo-original.jpg` (orijinal şablon). Açılışta SAMIX yükleme ekranı görünür ve oyun hazır olur olmaz kendiliğinden kapanır; dosya eksikse hata mesajı ve “Tekrar Dene” düğmesi çıkar.

## Kelime açıklaması (?)
Normal oyuncular rol ekranında gizli kelimenin yanındaki **?** simgesine dokunarak kısa bir açıklama görür. Imposter bu simgeyi görmez. Açıklamalar `aciklamalar.js` dosyasındadır (anahtar = kelime). Yeni kelime eklerseniz buraya da bir satır ekleyin; eklenmezse otomatik bir yedek metin gösterilir.

## Imposter-Seçimi (adil rastgele)
Her yeni turda imposter(lar) baştan ve rastgele seçilir; seçilebilen herkesin şansı eşittir. Tek kural: bir oyuncu üst üste 2 tur imposter olduysa, 3. turda dinlenir (yeterli başka oyuncu varsa). Böylece aynı kişi sürekli imposter olmaz. Yeni oyun başlatınca geçmiş sıfırlanır.

## Görünüm
Ayarlar → Görünüm: **Koyu** (varsayılan), **Açık** veya **Otomatik** (iPhone ayarını izler). iPhone’da Safari’de “Ana Ekrana Ekle” ile tam ekran uygulama gibi açılır.

## Modlar
- **Kelimeyi Bilmiyor:** Imposter kelimeyi görmez.
- **Benzer Kelime:** Imposter yakın ama farklı bir kelime alır (örn. Kedi–Köpek, İftar–Sahur). Seçili kategorilerde uygun çift yoksa otomatik olarak ilk moda geçilir.

## Dosyalar
`index.html`, `style.css`, `app.js` (arayüz), `logic.js` (oyun mantığı), `aciklamalar.js` (kelime açıklamaları), `assets/` (logo ve simgeler), `manifest.webmanifest`, `words.js` (1000+ kelime, 26 kategori, benzer kelime çiftleri). `tests/` klasörü isteğe bağlı otomatik testleri içerir (`node tests/test_logic.js`, `python3 tests/test_ui.py index.html`, `python3 tests/test_samix.py .`).

Ayarlar yalnızca bu cihazın tarayıcısında saklanır; hiçbir veri gönderilmez.

# Uğur Hoca Özel Ders & Eğitim Materyalleri Kuralları

Bu kurallar bu depoda üretilecek tüm matematik çalışma kağıtları, testler, fasiküller ve web uygulamaları için bağlayıcıdır ve tavizsiz uygulanır.

---

## 🛑 BASKI, DİZGİ VE SAYFA DÜZENİ DEMİR KURALLARI

### 1. Kesin Ham Kod / LaTeX Yasağı (Ders Kitabı Tipografisi)
- Üretilen hiçbir çalışma kağıdı, test, web sayfası veya fasikülde öğrencinin göreceği alanda `\frac{...}{...}`, `\cdot`, `\times`, `\div`, `\quad`, `\text{...}`, `^\circ\text{C}` veya `$...$` gibi ham LaTeX ve sözdizimi kodları **KESİNLİKLE BULUNAMAZ**.
- Tüm kesirler gerçek pay, payda ve kesir çizgisi içeren CSS (`<span class="frac"><span class="top">...</span><span class="bottom">...</span></span>`) veya MathJax ile render edilmelidir.
- Üslü sayılar (`²`, `³`, `⁴`, `⁵⁰`), çarpma (`×`, `·`), bölme (`÷`), derece (`°C`) ve ok işaretleri (`➔`) temiz Unicode / HTML olarak sunulmalıdır.

### 2. Soru ve İşlem Alanı Bölünmeme Kuralı (Anti-Split Standardı)
- Bir sorunun metni bir sayfada, işlem alanı diğer sayfada **ASLA KESİLEMEZ / BÖLÜNEMEZ**.
- Tüm soru kartlarına ve işlem kutularına `break-inside: avoid !important;` ve `page-break-inside: avoid !important;` uygulanmalıdır.
- Her sayfa tam A4 (297mm) ölçüsüne göre hesaplanmalı; bir sayfaya sığabilecek maksimum soru sayısı aşılmamalıdır:
  - **Başlıklı Sayfalarda:** En fazla **3 soru**.
  - **Başlıksız / Ara Sayfalarda:** En fazla **4 soru**.

### 3. Sayfayı Tam Dolduran Geniş İşlem Alanı (Flex-Grow / Boşluk Bırakmama Kuralı)
- Sorular sayfanın üstüne sıkıştırılıp altta atıl beyaz boşluk bırakılamaz.
- Sayfanın kalan tüm dikey yüksekliği (`flex: 1 1 0` ve `.work-grid-area { flex-grow: 1 }`), öğrencilerin rahatça yazı yazabilmesi için noktalı/kareli işlem alanlarına paylaştırılmalıdır.
- İşlem kutusu minimum yükseklikleri:
  - 3 sorulu sayfalarda: **175px - 200px**.
  - 4 sorulu sayfalarda: **130px - 150px**.

### 4. Kusursuz Yazdırma ve A4 Kilitleme Standardı (Print Geometry Standard)
- Yazdırma ve PDF çıktılarında `@page { size: A4 portrait; margin: 0; }` kullanılmalıdır. Kenar boşlukları doğrudan `.a4-page` container'ının padding değeri (`8mm 12mm 8mm 12mm`) ile milimetrik yönetilmelidir.
- `.a4-page` sınıfı baskıda `width: 210mm; height: 297mm; max-height: 297mm; box-sizing: border-box; overflow: hidden; page-break-after: always; break-after: page;` ile kilitlenmelidir.
- Flex child elemanlarına (`.page-questions-wrap`, `.question-card`, `.work-grid-area`) mutlaka `min-height: 0 !important;` verilmeli; böylece flex taşmaları ve sayfayı sonraki sayfaya iten domino kaymaları kesin olarak engellenmelidir.

### 5. Öğrenciye Dağıtım Ciddiyeti ve Sıfır Hata
- "Bu materyal doğrudan sınıfta öğrencilere basılıp dağıtılacak" ciddiyetiyle hareket edilmeli; kontrol edilmeden, ham kod kalıntısı veya sayfa taşması içeren hiçbir ürün tamamlandı denilerek teslim edilmemelidir.


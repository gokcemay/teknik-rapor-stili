---
name: teknik-rapor-stili
description: Google developer documentation style guide'ı teknik rapor türüne uyarlayan yazım ve düzenleme kuralları (Türkçe ve İngilizce). Teknik rapor, deney raporu, test raporu, proje ara/sonuç raporu, danışmanlık dönem raporu, fizibilite, SOP, teknik doküman veya kullanım kılavuzu yazılırken, mevcut bir raporun dili/biçimi denetlenirken, ya da bir raporun TR-EN çevirisi/ikinci dile uyarlaması yapılırken bu skill'i mutlaka kullan. Şu kısayollar doğrudan bu skill'i çağırır ve modu seçer — "/rapor" veya "rapor yaz" (Türkçe yazma), "/rapor-en" veya "report" (İngilizce yazma), "/stil" veya "stil kontrol" (denetim), "/duzelt" veya "raporu düzelt" (düzenleme), "/iskelet" (rapor iskeleti). Ayrıca "teknik rapor yaz", "bu metni rapor diline çevir", "technical report", "style check", "Google style" gibi ifadeler geçtiğinde de tetiklenir. Kullanıcı açıkça "stil kılavuzu" demese bile, çıktı bir teknik rapor veya teknik doküman ise bu kuralları uygula.
---

# Teknik rapor stili (TR / EN)

Bu skill, Google developer documentation style guide'ın (developers.google.com/style)
temel ilkelerini **teknik rapor** türüne uyarlar. Google kılavuzu geliştirici
dokümantasyonu için yazılmıştır; rapor türü farklı olduğu için bazı kurallar aynen
geçerlidir, bazıları bilinçli olarak değiştirilir. Nerede sapılacağı aşağıda ve
referans dosyalarında açıkça belirtilir.

## Komut kısayolları

Kullanıcı aşağıdaki kısayollardan birini yazarsa dil ve mod sorulmaz, doğrudan
belirlenir. Kısayolun ardından gelen metin veya dosya işlenecek girdidir.

| Kısayol | Dil | Mod | Davranış |
|---|---|---|---|
| `/rapor` | TR | yazma | `references/tr-style.md` + gerekiyorsa iskelet |
| `/rapor-en` | EN | yazma | `references/en-style.md` + gerekiyorsa iskelet |
| `/stil` | girdiden | denetim | Metni değiştirme, bulgu tablosu ver |
| `/duzelt` | girdiden | düzenleme | Düzeltilmiş metin + değişiklik özeti |
| `/iskelet` | girdiden | — | `assets/report-skeleton.md`'den uygun iskeleti ver |
| `/rapor-tr-en` | TR+EN | yazma | İki dilde; sayı, tarih, birim biçimlerini dönüştür |

Kısayolun ardından girdi yoksa tek bir soru sor: hangi rapor türü ve hangi
malzeme var. Uzun anket açma.

## Önce dili ve modu belirle

1. **Dil**: Metin Türkçe mi, İngilizce mi, yoksa iki dilli mi? Dil belirsizse
   kullanıcının yazdığı dili varsay.
2. **Mod**:
   - **Yazma modu** — sıfırdan rapor veya bölüm üretimi.
   - **Düzenleme modu** — var olan metni kurallara göre düzeltme.
   - **Denetim modu** — metni değiştirmeden bulguları listeleme.
   Kullanıcı belirtmemişse: metin verilmişse düzenleme, verilmemişse yazma modu.
3. Sonra ilgili referansı oku:
   - İngilizce çıktı → `references/en-style.md`
   - Türkçe çıktı → `references/tr-style.md`
   - Her iki dilde çıktı → ikisini de oku; sayı, tarih ve birim biçimleri
     dillerde **farklıdır**, birebir kopyalama.
   - Rapor iskeleti gerekiyorsa → `assets/report-skeleton.md`

## Her iki dilde geçerli çekirdek kurallar

Bunlar Google kılavuzundan doğrudan gelir ve rapor türünde de korunur:

- **Etken çatı ve açık özne**: Eylemi kimin/neyin yaptığı belli olsun. Türkçede
  akademik gelenek edilgen çatıyı zorlar; bunun sınırlı kullanımı için
  `references/tr-style.md`'ye bak.
- **Koşul önce, talimat sonra**: "Numune 60 °C'nin üzerindeyse ölçümü tekrarla",
  "Ölçümü tekrarla, eğer numune..." değil. Okuyucu koşulu bilmeden eylemi okumasın.
- **Cümle düzeni (sentence case)**: Başlıklarda yalnızca ilk harf ve özel adlar
  büyük. "Deney düzeneği ve yöntem" / "Test setup and method".
- **Belirsiz olmayan tarih**: 08/05/2026 gibi biçimleri asla kullanma.
- **Kod fontu**: Dosya adı, parametre, komut, sınıf/metot adı, konsol çıktısı ve
  yer tutucular kod fontunda. Yer tutucular `BUYUK_HARF_ALT_CIZGI` biçiminde.
- **Kalın yalnızca arayüz öğeleri ve satır içi alt başlıklar için**; vurgu
  gerekiyorsa italik, ama çoğu zaman kelimelerin kendisi vurguyu taşır.
- **Altı çizili yalnızca bağlantı metni için.**
- **Listeler**: Sıra önemliyse numaralı, değilse madde imli, terim-tanım
  çiftleri için tanım listesi. Her maddeyi paralel yapıda kur.
- **Bağlantı metni betimleyici olsun**: "buraya tıklayın" / "click here" değil,
  hedefin adı.
- **Abartılı iddia yok**: "Kesinlikle en iyi", "dramatik iyileşme", "significantly
  improved" gibi ifadeler ancak sayı ve istatistikle destekleniyorsa kullanılır.
  Aksi halde ölçülen değeri ver, yorumu okura bırak.
- **Zamansız içerik**: "Şu anda", "yakında", "yeni sürümde" gibi ifadeler raporu
  hızla eskitir. Tarih vermen gerekiyorsa açıkça yaz.
- **Küresel okuyucu**: Deyim, argo, kültürel gönderme, mizah kullanma. Kısaltmayı
  ilk geçtiği yerde aç.
- **Erişilebilirlik**: Her şekle alt metin; "aşağıdaki tabloda", "sağdaki grafik"
  gibi yalnızca konuma dayalı gönderme yerine numara ile gönder (Tablo 3, Şekil 2).

## Rapor türünde Google kılavuzundan bilinçli sapmalar

Google kılavuzu geliştiriciye seslenir; teknik rapor bir kuruma veya müşteriye
sunulur. Bu yüzden:

| Google kuralı | Raporda ne yapılır |
|---|---|
| İkinci tekil şahıs ("you") | Yalnızca prosedür/SOP adımlarında. Bulgu ve tartışma bölümlerinde nesnel anlatım kullan. |
| Sohbet havası, kısaltılmış biçimler ("don't", "it's") | Resmî register. İngilizcede kısaltılmış biçimleri kullanma; Türkçede konuşma dili kalıpları kullanma. |
| Şimdiki zaman | Sistem davranışı ve yöntem tarifi için şimdiki zaman; **yapılmış deney ve elde edilmiş bulgu için geçmiş zaman**. |
| Adım adım "how-to" yapısı | Rapor yapısı: amaç → yöntem → bulgu → tartışma → sonuç. `assets/report-skeleton.md`'ye bak. |

Ayrıca raporda Google'da olmayan iki zorunluluk vardır:

- **Belirsizlik ve ölçüm koşulu**: Her sayısal sonuç, ölçüm koşulu (yük, hız,
  mesafe, sıcaklık, nem) ve mümkünse tekrar sayısı ile belirsizlik/saçılım
  bilgisiyle birlikte verilir. Tek ölçümden genelleme yapma.
- **İzlenebilirlik**: Standart (ASTM, ISO), cihaz, numune kimliği ve ham veri
  dosyası adı raporda geçmelidir. Veri yoksa "veri mevcut değil" yaz; boşluğu
  tahminle doldurma.

## Veri dürüstlüğü

Rapor içeriği uydurulmaz. Kullanıcının vermediği ölçüm değeri, referans, standart
numarası veya kaynak üretme. Eksik bilgi için metinde `[VERİ: ...]` /
`[DATA: ...]` yer tutucusu bırak ve çıktının sonunda eksikleri listele.

## Denetim modu çıktısı

Metni yeniden yazmadan denetleniyorsa, bulguları şu tabloyla ver ve
en fazla 15 madde ile sınırla (en önemlileri önce):

| # | Konum | Bulgu | Önerilen düzeltme | Kural |
|---|---|---|---|---|

Sonuna 2-3 cümlelik genel değerlendirme ekle: hangi kalıp hata tekrarlanıyor.

## Düzenleme modu davranışı

- Kullanıcının kendi cümlelerini gereksiz yere yeniden yazma; yalnızca kurala
  aykırı olanı düzelt. Anlamı değiştirecek bir düzeltme gerekiyorsa düzeltmeyi
  yapma, soruyu sor.
- Düzenlenmiş metni ver, ardından "Yapılan başlıca değişiklikler" başlığı altında
  en fazla 8 maddelik özet ekle.
- Metin AI ile üretilmiş görünüyor ve Türkçeyse, `turkce-humanizer` skill'i varsa
  onu da devreye al.

## Çıktı biçimi

- Kısa bölüm veya denetim çıktısı: doğrudan sohbette.
- Tam rapor: dosya olarak üret (Markdown; kullanıcı LaTeX veya Word isterse o
  biçimde) ve `present_files` ile sun.
- Kullanıcı LaTeX kullanıyorsa matematiksel değişkenler italik, operatörler ve
  birimler dik yazılır (`\mathrm{}` veya `siunitx`).

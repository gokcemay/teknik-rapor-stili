# Türkçe teknik rapor stili

Google developer documentation style guide'ın ilkeleri Türkçe rapor türüne
uyarlanmıştır. Google kılavuzu İngilizce'ye özgü bazı kurallar içerir (Oxford
virgülü, Amerikan yazımı gibi); bunlar Türkçede **geçerli değildir** ve aşağıda
karşılıkları verilmiştir. Yazım için TDK Yazım Kılavuzu esas alınır.

İçindekiler:
1. Çatı, kişi ve zaman
2. Cümle ve paragraf kurgusu
3. Sözcük seçimi: bunları değiştir
4. Noktalama ve yazım
5. Sayı, birim ve tarih
6. Başlık, liste, tablo ve şekil
7. Kod, dosya adı ve yer tutucu
8. Terim yönetimi ve kaynak gösterme
9. Hızlı öz denetim

---

## 1. Çatı, kişi ve zaman

- **Etken çatı önceliklidir.** "Tribometre sürtünme katsayısını 10 ms aralıkla
  kaydetti" cümlesi, "kaydedilmiştir" biçiminden hem daha kısa hem daha açıktır.
- **Edilgen çatının meşru kullanımı**: Öznenin gerçekten önemsiz olduğu ya da
  kurumsal geleneğin zorunlu kıldığı yöntem bölümleri. Bu durumda bile edilgen
  yapıyı bölüm boyunca **tutarlı** kullan; bir paragrafta "ölçüldü", diğerinde
  "ölçtük" olmasın. Edilgen çatıyı, işi kimin yaptığını gizlemek için kullanma.
- **Kişi**: Raporda "ben" yok. "Biz" yalnızca kurum/ekip adına açık bir taahhüt
  verilirken kullanılır ("ETTOM olarak..."). İkinci çoğul şahıs ("yapınız",
  "dikkat ediniz") sadece prosedür, talimat ve SOP metinlerinde geçer.
- **Zaman**:
  - Yapılmış deney, gözlem, bulgu → **görülen geçmiş zaman** (-DI):
    "Üç numune alıştırma evresinde hasar gördü."
  - Genel geçer bilgi, sistem davranışı, verinin gösterdiği → geniş zaman:
    "DLC kaplamalar polimer altlıklarda adhezif aşınmayı azaltır."
    "Şekil 3, aşınma izi profilini gösterir."
  - **-mIş biçimini (öğrenilen geçmiş) kendi yaptığın iş için kullanma.**
    "Ölçülmüştür" kalıbı akademik gelenekte yaygındır ama raporda "ölçüldü"
    daha doğrudur; ikisini aynı metinde karıştırma.
  - Gelecek zaman yalnızca planlanan iş için ve tarih/faz belirterek kullanılır:
    "Faz 2 kapsamında PA6-GF numuneleri test edilecek (Ekim 2026)."
- **Kişileştirme yok.** Yazılım, cihaz ve veri "ister", "düşünür", "anlar",
  "karar verir" biçiminde anlatılmaz. "Denetleyici deneyi durdurur" doğru;
  "denetleyici yükün fazla olduğunu fark eder" yanlış.

## 2. Cümle ve paragraf kurgusu

- **Koşul önce, eylem sonra**: "Yüzey pürüzlülüğü Ra 1,6 µm'yi aşıyorsa
  parlatma adımı tekrarlanır." Tersi sırada okuyucu koşulu geç öğrenir.
- Cümle uzunluğu 15-25 sözcük. Türkçede yüklem sonda olduğu için uzun cümle
  İngilizceden daha çok yorar; 30 sözcüğü aşan cümleyi böl.
- Yüklemi geciktiren üst üste tamlama zincirlerinden kaçın. "Kaplama kalınlığı
  ölçüm sonuçlarının değerlendirilmesi çalışması" gibi üç katlı ad tamlamalarını
  fiile çevir: "Kaplama kalınlığı ölçümleri değerlendirildi."
- Paragraf 3-5 cümle, tek konu, konu cümlesi başta. Yalnızca ilk cümleleri okuyan
  biri raporun mantığını izleyebilmeli.
- Devrik cümle raporda kullanılmaz.
- Bağlaç yığmayı bırak: "ve ayrıca", "ancak buna rağmen", "yani dolayısıyla"
  gibi ikilemeler gereksizdir.

## 3. Sözcük seçimi: bunları değiştir

| Kullanma | Kullan |
|---|---|
| gerçekleştirmek (ölçüm/test için) | ölçmek, yapmak, uygulamak |
| icra etmek, ifa etmek | yapmak |
| sağlamak (her yerde) | eylemi adlandır: azaltır, artırır, mümkün kılar |
| ...ya yönelik olarak, ...ya ilişkin olarak | için, hakkında |
| bilindiği üzere, malumunuz | sil |
| unutulmamalıdır ki, belirtmek gerekir ki | sil, doğrudan bilgiyi yaz |
| önemli ölçüde (istatistiksiz) | ölçülen değişimi ver |
| ciddi anlamda, oldukça, son derece | sil veya sayı ver |
| dramatik iyileşme, devrim niteliğinde | ölçülebilir özelliği yaz |
| ve/veya | birini seç ya da "A, B veya her ikisi" |
| optimize etmek, domine etmek | iyileştirmek, baskın olmak |
| dizayn, ekipman, performans (gereksizse) | tasarım, donanım, başarım |
| adresslemek (address çevirisi) | ele almak, gidermek |
| aksiyon almak | önlem almak, harekete geçmek |
| deep dive, roadmap, insight | ayrıntılı inceleme, yol haritası, çıkarım |

Ek kurallar:

- "Bir" sözcüğünü İngilizce "a/an" çevirisi gibi her adın önüne koyma:
  "Bir numune hazırlandı" yerine "Numune hazırlandı".
- Sıfat yığmadan kaçın: "yüksek performanslı gelişmiş ileri kaplama" gibi
  zincirler bilgi taşımaz.
- Kısaltmayı ilk geçtiği yerde aç: "elmas benzeri karbon (diamond-like carbon,
  DLC)". Sonra yalnızca kısaltmayı kullan, tekrar açma.
- Yerleşmemiş İngilizce terimi ilk kullanımda parantezle ver: "aşınma izi
  (wear track)". Yerleşmiş terimi ("tribometre") çevirmeye çalışma.
- Türkçe karşılığı yerleşmiş terimde İngilizcesini kullanma: "sürtünme
  katsayısı", "coefficient of friction" değil.

## 4. Noktalama ve yazım

- **Oxford/seri virgülü Türkçede yoktur**: "kalınlık, sertlik ve yapışma".
  Son ögeden önce virgül konmaz.
- Özne ile yüklem arasına virgül konmaz. Sıralı cümleleri virgülle bağlarken
  öge sayısını sınırla.
- **Kesme işareti**: Özel ad ve kısaltmalara gelen çekim ekleri kesmeyle ayrılır:
  DLC'nin, ISO 4287'ye, ESOGÜ'de, 2026'da, 1 N'luk. Ancak yapım eki ve kurum adı
  eklerinde ayrılmaz: Türkçeleştirmek. Sayılara gelen ekte okunuşa uy:
  100 m'lik, 5'inci.
- Uzun çizgi (—) Türkçede ara söz için kullanılabilir ama seyrek kullan;
  parantez veya ayrı cümle çoğu zaman daha iyidir.
- Üç nokta ile cümle bitirme; eksik bilgiyi yer tutucuyla belirt.
- Tırnak içindeki alıntıda noktalama alıntının kendisine aittir; bağlantı
  metninin dışında kalır.
- Düzeltme işareti anlam ayrımı gerektiğinde korunur (hâlâ, kâr).
- Türkçe karakterleri (ç, ğ, ı, İ, ö, ş, ü) hiçbir koşulda kırpma; dosya adında
  ise Türkçe karakter kullanma (bkz. bölüm 7).

## 5. Sayı, birim ve tarih

- **Ondalık ayırıcı virgüldür**: 0,25. **Binlik ayırıcı noktadır**: 12.500.
  İngilizce metinde tam tersi olduğu için iki dilli raporda tabloları
  dönüştürmeyi unutma; en sık yapılan hata budur.
- Sayı ile birim arasına boşluk konur: 100 m, 25 °C, 1,5 GPa, 1 N.
  Yüzde işareti Türkçede sayıdan **önce** gelir: %12. Derece ve açı doğrudan
  bitişiktir: 45°.
- SI birimlerini doğru büyük/küçük harfle yaz: N, mm, s, °C, Pa. Birimden sonra
  nokta konmaz, birim çoğul yapılmaz ("5 mm", "5 mm'ler" değil).
- Birime gelen ek kesmeyle ve okunuşa göre: 10 N'luk yük, 100 m'lik kayma.
- Anlamlı basamak sayısı cihaz çözünürlüğüyle uyumlu olmalı; yazılımın bastığı
  bütün ondalıkları taşıma.
- Belirsizliği açıkça ver: "0,42 ± 0,03 (n = 3, standart sapma)".
- Aralık: "20 °C ile 80 °C arasında" veya "20-80 °C". "20 ile 80 °C arası" gibi
  yarım bırakılmış kalıplardan kaçın.
- **Tarih**: Metinde "18 Ağustos 2026". Tablo, kayıt ve dosya adında ISO 8601
  (`2026-08-18`). 18.08.2026 biçimi kurum yazışmasında kabul edilebilir ama
  raporun tamamında tek biçim kullanılır; 08/05/2026 gibi belirsiz biçim asla.
- **Saat**: 24 saat düzeni, gerekiyorsa dilim: 14:30 (UTC+3).
- Matematiksel değişken italik, işleç ve birim dik yazılır: *v* = 0,1 m/s.

## 6. Başlık, liste, tablo ve şekil

**Başlıklar**

- Türkçede başlıkta yalnızca ilk sözcüğün ilk harfi ve özel adlar büyük yazılır:
  "Deney düzeneği ve yöntem". Her sözcüğü büyük harfle başlatma.
- Başlık tek başına anlaşılır olmalı; içindekiler listesinde okunduğunda ne
  anlattığı belli olsun.
- Bölüm başlığından hemen sonra "Bu bölümde bunlar ele alınmıştır" gibi boş
  cümle kurma; başlığın ardındaki ilk cümle "Bu" ile başlayıp başlığa
  gönderme yapmasın.
- Başlık sonuna nokta konmaz.

**Listeler**

- Sıra ve adım varsa numaralı, yoksa madde imli, terim-tanım çifti için tanım
  listesi kullan.
- Her listeyi iki nokta ile biten bir giriş cümlesiyle tanıt.
- Maddeler paralel olsun: hepsi ad öbeği ya da hepsi emir kipi.
- Maddelerden biri tam cümleyse hepsini noktayla bitir; hiçbiri değilse hiçbirini
  noktalama.
- 2-9 madde uygundur; daha uzun listeyi gruplandır veya tabloya çevir.

**Tablolar**

- Tablo başlığı **üstte** ve numaralı: "Tablo 3. Pin-on-disk deney parametreleri."
- Her tabloya metinde, tablodan önce gönderme yapılır.
- Birim sütun başlığında verilir, her hücrede tekrarlanmaz: "Yük (N)".
- Sayılar ondalık ayırıcıya göre hizalanır; sütun boyunca ondalık basamak sayısı
  sabit tutulur. Eksik veri için boş hücre bırakma; "-" veya "ölçülmedi" yaz.
- Tek sütunlu tablo aslında listedir; tabloya gerek yok.

**Şekiller**

- Şekil açıklaması **altta** ve numaralı: "Şekil 2. Baskı hâlindeki ABS
  numunesinin aşınma izi profili."
- Alt metin şeklin ne gösterdiğini anlatır ("grafik", "görsel" demek yetmez).
- Mikroyapı görüntülerinde ölçek çubuğu, grafiklerde birimli eksen etiketi
  zorunludur.
- Serileri yalnızca renkle ayırma; işaretçi veya çizgi tipi de değişsin.
- Vektörel (SVG, PDF) veya yüksek çözünürlüklü görsel kullan.

## 7. Kod, dosya adı ve yer tutucu

- Dosya adı, yol, parametre, komut, fonksiyon/sınıf adı, konsol çıktısı ve
  ortam değişkenleri kod fontunda yazılır.
- Yer tutucular büyük harf ve alt çizgiyle, kod fontunda: `NUMUNE_KODU`,
  `CIKTI_YOLU`. Her yer tutucu bloğun hemen ardından açıklanır.
- Kod bloğu iki nokta ile biten bir cümleyle tanıtılır.
- Atlanan kod, üç nokta yerine dilin yorum satırıyla belirtilir.
- Dosya adlarında Türkçe karakter, boşluk ve büyük harf kullanma; küçük harf ve
  tire yeterlidir: `abs-xy-asinma-2026-08-18.csv`.

## 8. Terim yönetimi ve kaynak gösterme

- Rapor başına bir terim listesi tut; aynı kavram için iki farklı Türkçe karşılık
  kullanma (hem "yapışma" hem "adezyon" olmasın; birini seç, diğerini ilk
  kullanımda parantezle ver).
- Standartları tam künyesiyle an: "ASTM G99-23", "ISO 4287:1997".
- Kaynağı ikinci elden özet yerine aslından göster.
- Tek atıf biçimi kullan (IEEE, APA veya derginin şablonu) ve rapor boyunca
  değiştirme.
- İç göndermeler numaralı ögeyle yapılır: "bkz. Bölüm 3.2", "Tablo 4".
  "Yukarıda belirtildiği gibi" biçimi sayfa düzeni değişince anlamını yitirir.

## 9. Hızlı öz denetim

Teslimden önce doğrula:

1. Her iddianın arkasında sayı, kaynak ya da açık bir çıkarım ifadesi var.
2. Ondalık virgül / binlik nokta rapor boyunca tutarlı; İngilizce kaynaktan
   kopyalanmış nokta-ondalıklar dönüştürülmüş.
3. Kesme işaretleri doğru: DLC'nin, 2026'da, 100 m'lik.
4. Başlıklar cümle düzeninde, her sözcük büyük harfle başlamıyor.
5. Şekil ve tabloların tamamı numaralı, açıklamalı ve metinde anılmış.
6. Kısaltmalar ilk kullanımda bir kez açılmış.
7. Zaman kullanımı tutarlı; "-mIş" ile "-DI" karışmıyor.
8. Dolgu kalıpları (bölüm 3) temizlenmiş.
9. Her ölçüm sonucunun yanında deney koşulu ve belirsizlik bilgisi var.
10. Metin AI üretimi izleri taşımıyorsa doğal Türkçe ritmi korunmuş; gerekirse
    `turkce-humanizer` skill'i ile son geçiş yapılmış.

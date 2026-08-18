# teknik-rapor-stili

Teknik rapor yazımı için Türkçe ve İngilizce stil kuralları içeren bir Claude
skill'i. Kurallar, Google developer documentation style guide'ın
([developers.google.com/style](https://developers.google.com/style)) ilkelerinden
türetilmiş ve rapor türüne uyarlanmıştır.

*A Claude skill with Turkish and English style rules for technical report
writing, adapted from the Google developer documentation style guide.*

## Ne işe yarar

Skill, üç modda çalışır:

- **Yazma** — sıfırdan rapor veya bölüm üretimi
- **Düzenleme** — var olan metni kurallara göre düzeltme, değişiklik özetiyle
- **Denetim** — metni değiştirmeden bulguları tablo hâlinde listeleme

Kapsadığı doküman türleri: deney/test raporu, proje ara ve sonuç raporu,
danışmanlık dönem raporu, fizibilite raporu, SOP ve teknik doküman.

## Kurulum

**Claude Code'da (tek komutla):**

```
/plugin marketplace add gokcemay/teknik-rapor-stili
/plugin install teknik-rapor-stili@gokcemay-plugins
```

Kurulum sonrası `Run /reload-plugins to activate.` uyarısı çıkarsa `/reload-plugins`
komutunu çalıştırın. Slash komutları eklenti adıyla ad alanına girer:
`/teknik-rapor-stili:rapor`, `/teknik-rapor-stili:stil` gibi.

**Claude uygulamasında:** `dist/teknik-rapor-stili.skill` dosyasını indirin,
sohbete yükleyip **Save skill** düğmesine basın. Uygulamada sohbete komut yazarak
kurulum yapılamaz; kurulum kullanıcı onayıyla arayüzden yapılır.

**Elle kurulum (Claude Code, eklenti istemeyenler için):**

```bash
git clone https://github.com/gokcemay/teknik-rapor-stili.git /tmp/trs
cp -r /tmp/trs/plugins/teknik-rapor-stili/skills/teknik-rapor-stili ~/.claude/skills/
cp /tmp/trs/plugins/teknik-rapor-stili/commands/*.md ~/.claude/commands/
```

Skill, "teknik rapor yaz", "raporu düzenle", "stil kontrolü yap",
"technical report", "style check" gibi ifadelerde kendiliğinden devreye girer.

## Kısayollar

| Kısayol | Ne yapar |
|---|---|
| `/rapor` | Türkçe rapor yazar |
| `/rapor-en` | İngilizce rapor yazar |
| `/stil` | Metni değiştirmeden stil denetimi yapar, bulgu tablosu verir |
| `/duzelt` | Metni kurallara göre düzeltir, değişiklik özeti ekler |
| `/iskelet` | Rapor türüne uygun iskeleti verir |
| `/rapor-tr-en` | İki dilde yazar, sayı ve tarih biçimlerini dönüştürür |

Claude uygulamasında bu kısayollar düz metin olarak çalışır (`/rapor` yazmak
yeterli). Claude Code'da eklenti kuruluysa gerçek slash komutu olarak listelenir
ve ad alanı önekiyle çağrılır: `/teknik-rapor-stili:rapor`.

## Yapı

```
teknik-rapor-stili/
├── .claude-plugin/
│   └── marketplace.json          # eklenti kataloğu (marketplace)
├── plugins/teknik-rapor-stili/
│   ├── .claude-plugin/plugin.json
│   ├── skills/teknik-rapor-stili/
│   │   ├── SKILL.md              # dil ve mod seçimi, ortak çekirdek kurallar
│   │   ├── references/
│   │   │   ├── tr-style.md       # Türkçe kurallar
│   │   │   └── en-style.md       # İngilizce kurallar
│   │   └── assets/
│   │       └── report-skeleton.md  # rapor iskeletleri
│   └── commands/                 # slash komutları
└── dist/
    └── teknik-rapor-stili.skill  # Claude uygulaması için kurulabilir paket
```

Progressive disclosure ilkesine göre yalnızca ilgili dil dosyası okunur; iki
dilli rapor yazılırken ikisi birden yüklenir.

## Google kılavuzundan neyi aldık, neyi değiştirdik

Aynen korunanlar: etken çatı, koşul-önce-talimat-sonra sıralaması, cümle
düzeninde başlıklar, liste türleri ve paralel yapı, kod fontu kuralları, büyük
harfli yer tutucular, betimleyici bağlantı metni, abartılı iddia yasağı,
zamansız içerik, erişilebilirlik ve küresel okuyucu ilkeleri.

Rapor türü için değiştirilenler:

| Google kuralı | Bu skill'de |
|---|---|
| İkinci tekil şahıs ("you") | Yalnızca prosedür ve SOP adımlarında |
| Sohbet havası, kısaltılmış biçimler | Resmî register |
| Her şey şimdiki zamanda | Yapılmış deney geçmiş, genel bilgi geniş zamanda |
| Adım adım "how-to" yapısı | Amaç → yöntem → bulgu → tartışma → sonuç |

Rapora özgü iki ek zorunluluk: her ölçüm sonucunun yanında deney koşulu ve
belirsizlik bilgisi; standart, cihaz, numune kimliği ve ham veri dosyası adıyla
izlenebilirlik.

Türkçeye taşınmayan İngilizce kurallar: Oxford virgülü ve ondalık ayırıcı.
Türkçede ondalık virgül ile binlik nokta, İngilizcede tersi kullanılır; iki dilli
raporlarda en sık kaçan hata budur ve iki referans dosyasında da uyarı vardır.

## Katkı

Kural önerileri ve düzeltmeler için issue açın. Bir kural önerirken hangi
duruma ait olduğunu ve karşı örneğini de yazarsanız değerlendirmek kolaylaşır.

## Lisans

Bu depo [CC BY 4.0](LICENSE) ile lisanslanmıştır. İçerik, Creative Commons
Attribution 4.0 lisanslı Google developer documentation style guide'dan türetilmiş
uyarlamalar içerir. Bkz. [NOTICE.md](NOTICE.md).

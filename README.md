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

## Claude Code'da kullanım (eklenti)

Kurulum iki komut. Terminalde `/plugin` paneli açılmıyorsa (desktop uygulaması
veya bulut oturumu) kabuk sürümünü kullanın:

```
/plugin marketplace add gokcemay/teknik-rapor-stili
/plugin install teknik-rapor-stili@gokcemay-plugins
```

```bash
claude plugin marketplace add gokcemay/teknik-rapor-stili
claude plugin install teknik-rapor-stili@gokcemay-plugins
```

Kabuk sürümüyle kurduysanız eklenti bir sonraki oturumda yüklenir. Açık bir
oturum varsa `/reload-plugins`, uyarı verirse `/reload-plugins --force` çalıştırın.
Desktop uygulamasında komutlar görünmüyorsa uygulamayı bildirim alanından
tamamen kapatıp yeniden açın.

Komutlar eklenti adıyla ad alanına girer:

| Komut | Ne yapar |
|---|---|
| `/teknik-rapor-stili:rapor` | Türkçe rapor veya bölüm yazar |
| `/teknik-rapor-stili:rapor-en` | İngilizce rapor veya bölüm yazar |
| `/teknik-rapor-stili:stil` | Metni değiştirmeden denetler, bulgu tablosu verir |
| `/teknik-rapor-stili:duzelt` | Metni düzeltir, değişiklik özeti ekler |
| `/teknik-rapor-stili:iskelet` | Rapor türüne uygun iskeleti verir |

Komutun ardına metni veya dosya yolunu ekleyin:

```
/teknik-rapor-stili:stil raporlar/agustos-donem-raporu.md
/teknik-rapor-stili:iskelet fizibilite
```

Komut kullanmadan da çalışır: "bu bölümü rapor diline çevir" gibi bir istekte
skill kendiliğinden devreye girer.

**Eklenti istemeyenler için elle kurulum:**

```bash
git clone https://github.com/gokcemay/teknik-rapor-stili.git /tmp/trs
cp -r /tmp/trs/plugins/teknik-rapor-stili/skills/teknik-rapor-stili ~/.claude/skills/
cp /tmp/trs/plugins/teknik-rapor-stili/commands/*.md ~/.claude/commands/
```

## Claude uygulamasında kullanım (skill)

`dist/teknik-rapor-stili.skill` dosyasını indirin, sohbete yükleyin ve dosya
kartındaki **Save skill** düğmesine basın. Sohbete komut yazarak kurulum
yapılamaz; kurulum kullanıcı onayıyla arayüzden geçer.

Kurulduktan sonra kısayollar düz metin olarak çalışır — ad alanı öneki gerekmez:

| Kısayol | Ne yapar |
|---|---|
| `/rapor` | Türkçe rapor yazar |
| `/rapor-en` | İngilizce rapor yazar |
| `/stil` | Metni değiştirmeden denetler |
| `/duzelt` | Metni düzeltir, değişiklik özeti ekler |
| `/iskelet` | Rapor iskeleti verir |
| `/rapor-tr-en` | İki dilde yazar, sayı ve tarih biçimlerini dönüştürür |

Örnek:

```
/stil
[denetlenecek paragrafı buraya yapıştırın]
```

Uzun bir raporu dosya olarak yükleyip `/duzelt` yazmak da çalışır.

## Claude dışındaki araçlarda kullanım

Skill'in içeriği düz Markdown olduğu için başka ortamlarda da kullanılabilir.
Otomatik tetikleme yalnızca Claude'da çalışır; diğer araçlarda ilgili dosyayı
siz yüklersiniz.

**Kod editörleri (Cursor, Windsurf, Copilot ve benzerleri):** proje kökündeki
kural veya talimat dosyasına `references/tr-style.md` ya da `references/en-style.md`
içeriğini kopyalayın. `AGENTS.md` konvansiyonunu kullanan araçlarda bu dosyaya
"Teknik rapor yazarken şu kurallara uy" başlığıyla ekleyin. Tek dosya sınırı
varsa yalnızca çalıştığınız dilin referansını koyun; ikisi birden gereksiz
bağlam yükü yaratır.

**ChatGPT, Gemini ve benzeri sohbet araçları:** ilgili referans dosyasını proje
talimatı, özel yönerge (custom instructions) veya Gem tanımı olarak yapıştırın.
Uzunluk sınırına takılırsanız dosyanın 9. bölümündeki "Hızlı öz denetim"
listesiyle başlayın; en çok işi o bölüm görür.

**Yerel modeller (Ollama, LM Studio ve benzerleri):** referans dosyasını sistem
istemi olarak verin. Bağlam penceresi darsa SKILL.md'nin çekirdek kurallar
bölümü ile tek dil referansı yeterlidir.

**İnsan ekipler için:** dosyalar eklentiden bağımsız birer yazım kılavuzu olarak
okunabilir. `references/tr-style.md` ve `references/en-style.md` kurum içi stil
kılavuzu olarak dağıtılabilir; `assets/report-skeleton.md` rapor şablonu olarak
kullanılabilir. Lisans buna izin verir, atıf yeterlidir.

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

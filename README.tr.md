# Akademik Araştırma Promptları

[English](README.md) | **Türkçe**

Bir yapay zekâ asistanını her söylenene katılan bir yardımcı olmaktan çıkarıp eleştirel bir araştırma asistanı gibi çalıştıran dokuz prompt. Literatür taramasından gönderim öncesi hakem değerlendirmesine kadar uzanan süreci kapsar.

## Nasıl kullanılır

1. **Prompt 0**'ı yapay zekâ aracınızın proje ya da özel talimatlar (custom instructions) alanına bir kez yapıştırın. Sonraki tüm adımlarda geçerli olur.
2. Promptları sırayla kullanın. Her biri aşağıdaki iş akışının bir adımına karşılık gelir.
3. Göndermeden önce `[KÖŞELİ PARANTEZ İÇİNDEKİ]` her alanı kendi içeriğinizle değiştirin.
4. 1, 2, 3 ve 7 numaralı promptlar için web'de arama yapabilen bir araç kullanın ("deep research" ya da "search" modu). Arama yapamayan bir model yalnızca belleğinden yanıt verebilir; uydurma atıflar da tam olarak buradan kaynaklanır.
5. Modelin verdiği her DOI'yi ya da bağlantıyı, atıf yapmadan önce açıp kontrol edin. Bu promptlar uydurma kaynakları azaltır, ancak tamamen ortadan kaldırmaz.

## İş akışı

| Adım | Ne yaparsınız | Prompt |
|---|---|---|
| 1 | Alanda bilinenleri öğrenin | [1. Literatür taraması](#1-literatür-taraması) |
| 2 | Çözülmemiş problemleri bulun | [2. Araştırma boşluğu analizi](#2-araştırma-boşluğu-analizi) |
| 3 | Fikrinizin daha önce ortaya konup konmadığını kontrol edin | [3. Önceki çalışma taraması](#3-önceki-çalışma-taraması) |
| 4 | Fikri yanlışlanabilir bir hipoteze dönüştürün | [4. Hipotez geliştirme](#4-hipotez-geliştirme) |
| 5 | Modeli ve deneyleri tasarlayın | [5. Deney tasarımı](#5-deney-tasarımı) |
| 6 | Deneyleri yürütün ve sonuçları ölçün | Kendi çalışmanız |
| 7 | Göndermeden önce çalışmanızı eleştirin | [8. Hakem değerlendirmesi](#8-hakem-değerlendirmesi) |

İki prompt her adımda işe yarar: tek bir makaleyi ayrıntısıyla anlamanız gerektiğinde [6. Makalenin derinlemesine analizi](#6-makalenin-derinlemesine-analizi), kendiniz kontrol etmediğiniz bir kaynakçanız olduğunda ise [7. Atıf doğrulama](#7-atıf-doğrulama).

---

## 0. Genel talimatlar

Proje ya da özel talimatlar alanına bir kez yapıştırın.

```text
Sen benim akademik araştırma asistanımsın. Araştırmayla ilgili tüm görevlerde aşağıdaki ilkelere uy.

Doğruluk
1. Bilimsel doğruluk, benimle aynı fikirde olmaktan önce gelir.
2. Asla atıf, DOI, matematiksel sonuç ya da deneysel bulgu uydurma.
3. Bilgileri birincil akademik kaynaklarla doğrula ve hakemli yayınlara öncelik ver.
4. Arama aracın yoksa ya da bir kaynağa erişemiyorsan bunu açıkça belirt. Doğrulanmamış olarak işaretlemeden boşluğu bellekten doldurma.
5. Her kaynak için tam metnini mi okuduğunu, yalnızca özetini mi okuduğunu, yoksa bellekten mi hatırladığını belirt.
6. Mümkün olan her durumda her kaynak için doğrudan bağlantı ya da DOI ver.

Akıl yürütme
7. Kanıtlanmış olguları, hipotezleri, varsayımları, yorumları ve spekülasyonları birbirinden açıkça ayır.
8. Yeterli kanıt olmadan korelasyonu asla nedensellik olarak yorumlama.
9. Ara matematiksel türetmeleri atlama. Kesin bir gösterim ve yerleşik terminoloji kullan.
10. Varsayımlarımı sorgula ve hipotezimle çelişen kanıtları etkin biçimde ara.
11. Yeterli literatür doğrulaması yapmadan asla bilimsel özgünlük iddia etme.
12. Belirsizlikleri ya da sınırlılıkları asla gizleme.

Üslup
13. Hesaplama kolaylığı yerine bilimsel titizliğe öncelik ver ve önerdiğin deneylerin tekrarlanabilir olmasını sağla.
14. Övgüden, tekrardan ve dolgu cümlelerinden kaçın.

Amacın haklı olduğumu kanıtlamak değil, bilimsel olarak doğru olanı bulmama yardım etmektir.
```

## 1. Literatür taraması

```text
Kapsamlı ve eleştirel bir literatür taraması yap.

Araştırma alanı: [ARAŞTIRMA ALANI]
Araştırma konusu: [KONU]
Kapsanacak yayın yılları: [YIL ARALIĞI]
Dahil et: [DAHİL ETME ÖLÇÜTLERİ, ör. hakemli dergi ve konferans makaleleri]
Hariç tut: [HARİÇ TUTMA ÖLÇÜTLERİ, ör. İngilizce olmayan makaleler, çalıştay özetleri]
Çıktı dili: [DİL]

Arama
1. Araçlarının izin verdiği ölçüde IEEE Xplore, ACM Digital Library, ScienceDirect, SpringerLink, Wiley, Google Scholar ve arXiv'de arama yap.
2. Hem temel çalışmalara hem de en güncel yayınlara yer ver.
3. Hakemli dergi makalelerine ve saygın konferans bildirilerine öncelik ver.
4. Mümkün olduğunda özetlere güvenmek yerine tam metni oku.
5. İlgili başka çalışmaları bulmak için geriye ve ileriye doğru atıf zincirlerini takip et.
6. Arama yapamıyorsan ya da bir kaynağı açamıyorsan devam etmeden önce bunu belirt. Bellekten bir makale listesi oluşturup bunu arama sonucu gibi sunma.

İlgili her yayın için şunları ver
1. Başlık, yazarlar, yıl, yayın yeri ve DOI ya da bağlantı.
2. Erişim düzeyi: tam metin okundu, yalnızca özet okundu ya da doğrulanmadı.
3. Araştırma problemi.
4. Yöntem.
5. Deney düzeneği ve varsayımlar.
6. Nicel bulgular.
7. Sınırlılıklar.
8. Benim araştırmamla ilgisi.

Sentez
1. Yayınları bir tabloda sistematik olarak karşılaştır.
2. Çelişen bulguları belirle ve olası nedenlerini açıkla.
3. Yeterince araştırılmamış araştırma yönlerini öne çıkar.
4. Tek tek özetlerin bir derlemesiyle değil, eleştirel bir sentezle bitir.

Arama raporu
1. Kullandığın arama sorgularını ve gerçekten erişebildiğin veritabanlarını listele.
2. Kapsamının ve tam metin erişiminin sınırlarını belirt.

Yayın, yazar, DOI, deneysel sonuç ya da atıf uydurma. Doğrulanmış bulguları kendi yorumlarından ve varsayımlarından açıkça ayır.
```

## 2. Araştırma boşluğu analizi

```text
Mevcut literatürdeki kanıtlara dayanarak aşağıdaki alanda bilimsel açıdan anlamlı araştırma boşluklarını belirle.

Araştırma alanı: [ARAŞTIRMA ALANI]
Varsa daha dar odak: [ODAK]
Çıktı dili: [DİL]

Şunları incele
1. Çözülmemiş kuramsal problemler.
2. Yöntemsel sınırlılıklar.
3. Gerçekçi olmayan deneysel varsayımlar.
4. Çelişen ampirik sonuçlar.
5. Yetersiz karşılaştırmalı değerlendirme (benchmarking).
6. Ölçeklenebilirlik ve genelleme sorunları.
7. Yeterince incelenmemiş çalışma koşulları.
8. Disiplinlerarası yaklaşımlar için fırsatlar.

Her boşluk için şunları ver
1. Boşluğun tanımı.
2. Atıflar ve DOI ya da bağlantılarla destekleyici kanıtlar.
3. Problemin neden hâlâ çözülmediği.
4. Olası bir araştırma sorusu.
5. Önerilen yöntem.
6. Gerekli matematiksel ve teknik altyapı.
7. Hesaplama ve deney gereksinimleri.
8. Beklenen bilimsel katkı.
9. Riskler ve sınırlılıklar.

Her boşluğu bilimsel özgünlük, bilimsel önem, teknik uygulanabilirlik, yayın potansiyeli ve [YÜKSEK LİSANS / DOKTORA] tezine uygunluk açısından 1 ile 10 arasında puanla. Her puanı kanıtla gerekçelendir; bir puan kaba bir tahminse bunu belirt.

Tekniklerin daha önce denenmemiş bir birleşimini varsayılan olarak anlamlı bir bilimsel katkı sayma. Kimsenin üzerinde çalışmadığı bir boşluk, üzerinde çalışmaya değmeyen bir boşluk da olabilir; her boşluk için bu olasılığı ele al.

Literatürde arama yapamıyorsan bunu belirt ve öne sürdüğün her boşluğu doğrulanmamış olarak işaretle.
```

## 3. Önceki çalışma taraması

```text
Titiz bir önceki çalışma (prior art) taraması yürüten bağımsız bir hakem gibi davran. Amacın fikrimi onaylamak değil, bilimsel katkısının yeni olup olmadığını belirlemektir.

Önerdiğim araştırma fikri:
[ARAŞTIRMA FİKRİNİN AYRINTILI AÇIKLAMASI]

Çıktı dili: [DİL]

Arama
1. Aynı, benzer ve kavramsal olarak eşdeğer yaklaşımları ara.
2. Alternatif terimlerle, eş anlamlı ifadelerle ve komşu alanların terminolojisiyle arama yap.
3. Yayınları, tezleri, ön baskıları (preprint) ve ilgili patentleri kapsa.
4. Erişilebildiği her durumda en yakın çalışmaların tam metnini oku ve başlıklarını ya da özetlerini değil, gerçek yöntemlerini karşılaştır.
5. Tek tek bileşenlerin ya da bunların birleşiminin daha önce önerilip önerilmediğini kontrol et.
6. Kullandığın arama sorgularını listele.

İlgili her çalışmayla örtüşmeyi şunlardan biri olarak sınıflandır
1. Aynı yaklaşım
2. Yöntemsel olarak büyük ölçüde örtüşme
3. Kısmi örtüşme
4. Kavramsal benzerlik
5. Kayda değer örtüşme yok

Ardından
1. Önerimle mevcut çalışmalar arasındaki farkları gösteren bir karşılaştırma matrisi oluştur.
2. Varsa hangi yönlerin savunulabilir özgün bir katkı oluşturduğunu belirt.
3. Fikir daha önce uygulanmışsa bunu açıkça söyle.

Şüpheci ol. Özgünlüğü abartma, araştırma boşluğu uydurma ya da kanıt olmadan beni rahatlatmaya çalışma. Kanıt bulunamamasını, yokluğun kanıtıyla karıştırma: hiçbir şey bulamadıysan aramayı ne kadar kapsamlı yapabildiğini ve nelere erişemediğini belirt.
```

## 4. Hipotez geliştirme

```text
Bir araştırma fikrini kesin ve yanlışlanabilir bir hipoteze dönüştürmeme yardım et.

Ele almak istediğim araştırma boşluğu: [ARAŞTIRMA BOŞLUĞU]
Fikrim: [FİKİR]
En yakın mevcut çalışmalar: [ÖNCEKİ ÇALIŞMA TARAMASINDAN TEMEL ÇALIŞMALAR]
Çıktı dili: [DİL]

Şunları yap
1. Araştırma sorusunu tek cümleyle ifade et.
2. Bir deneyle yanlışlanabilecek tek bir ana hipotez oluştur. Yalnızca gerekliyse ikincil hipotezler ekle.
3. Hipotezdeki her terimi işlevsel olarak tanımla: neyin, hangi birimle ve hangi koşullar altında ölçüldüğünü belirt.
4. Beklenen etkiyi ve yönünü, bu etkiyi öngören kuramsal gerekçeyle birlikte belirt.
5. Hipotezi yanlışlayacak somut gözlemi tanımla.
6. Hipotezin dayandığı varsayımları listele ve her biri geçersiz çıkarsa ne olacağını açıkla.
7. Aynı sonucu doğurabilecek alternatif açıklamaları ver ve bunların birbirinden nasıl ayırt edileceğini belirt.
8. En yakın mevcut çalışmalarla karşılaştırıldığında tam olarak neyin yeni olduğunun iddia edildiğini belirt.
9. Hipotezin belirsiz, test edilemez ya da tanım gereği doğru olduğu her yerde onu yeniden yaz.

Hipotezi, arkasındaki gerekçeden daha güçlü gösterme. Fikir henüz test edilebilir bir hipotezi desteklemiyorsa bunu söyle ve neyin eksik olduğunu belirt.
```

## 5. Deney tasarımı

```text
Hipotezimi değerlendirmek için titiz ve tekrarlanabilir bir deney çerçevesi tasarla.

Hipotez: [HİPOTEZ]
Önerilen yöntem: [YÖNTEM]
Mevcut kaynaklar: [HESAPLAMA, VERİ, EKİPMAN, ZAMAN]
Çıktı dili: [DİL]

Şunları belirt
1. Sıfır hipotezi ve alternatif hipotez.
2. Bağımsız, bağımlı ve kontrol değişkenleri.
3. Matematiksel sistem modeli.
4. Deneysel varsayımlar.
5. Karşılaştırma (baseline) yöntemleri ve her birinin neden adil bir karşılaştırma olduğu.
6. Parametre aralıkları.
7. Değerlendirme ölçütleri.
8. Örneklem büyüklüğü ve istatistiksel güç.
9. Uygun olduğu durumlarda Monte Carlo simülasyonu gereksinimleri.
10. İstatistiksel anlamlılık testleri ve güven aralıkları.
11. Ablasyon çalışmaları.
12. Duyarlılık analizi.
13. Hesaplama karmaşıklığı.
14. Tekrarlanabilirlik gereksinimleri: kod, rastgele tohum değerleri (random seed), veri ve çalışma ortamı.

Ayrıca
1. Olası karıştırıcı değişkenleri, veri sızıntısını, seçim yanlılığını ve adil olmayan karşılaştırmaları belirle.
2. Hipotezimi yalnızca doğrulayabilecek değil, yanlışlayabilecek deneyler de tasarla.
3. Herhangi bir deney yürütülmeden önce, önerilen yöntemin hangi koşullar altında başarısız sayılması gerektiğini tanımla.

Sentetik deney sonuçları üretip bunları gerçek bulgular gibi sunma.
```

## 6. Makalenin derinlemesine analizi

Makalenin PDF dosyasını ekleyin ya da tam metnini yapıştırın.

```text
Ekteki araştırma makalesini eleştirel olarak analiz et. Yalnızca özetlemekle yetinme.

Çıktı dili: [DİL]

Şunları açıkla
1. Temel araştırma problemi.
2. Kuramsal ve matematiksel temeller.
3. Önerilen yöntem.
4. Önemli her denklem ve türetilişi, ara işlemleri atlamadan adım adım.
5. Yazarların yaptığı varsayımlar.
6. Deney tasarımı.
7. Veri kümeleri, parametreler ve değerlendirme ölçütleri.
8. Karşılaştırma (baseline) yöntemleri.
9. Sonuçların istatistiksel geçerliliği.
10. Gerçek bilimsel katkı.
11. Yöntemsel zayıflıklar.
12. Deneylerin tekrarlanabilirliği.
13. Kanıtlarla yeterince desteklenmeyen iddialar.

Yazarların iddia ettiklerini, sonuçlarının gerçekte gösterdiklerinden ayır. Her nokta için sayfa, bölüm, denklem, şekil ya da tablo belirt. Makalenin bir kısmı okunamıyorsa ya da sağladığım metinde eksikse, içeriğini tahmin etmek yerine bunu belirt.

Son olarak yöntemin nasıl yeniden üretilebileceğini, genişletilebileceğini ya da geliştirilebileceğini açıkla.
```

## 7. Atıf doğrulama

Bu promptu, bir yapay zekâ aracından gelen ya da kendiniz kontrol etmediğiniz her kaynakça için kullanın.

```text
Aşağıdaki kaynakları ve bunlara dayandırılan iddiaları doğrula. Kontrol etmediğin hiçbir şeyi doğru kabul etme.

Kaynaklar ve iddialar:
[KAYNAKÇA, HER KAYNAK İÇİN DAYANAK GÖSTERİLDİĞİ İDDİAYLA BİRLİKTE]

Çıktı dili: [DİL]

Her kaynak için şunları kontrol et
1. Yayının var olup olmadığı.
2. Başlık, yazarlar, yıl, yayın yeri ve DOI bilgilerinin doğru olup olmadığı. Doğru değilse düzeltilmiş hâllerini ver.
3. DOI'nin ya da bağlantının o yayına gidip gitmediği.
4. Yayının, dayanak gösterildiği iddiayı gerçekten destekleyip desteklemediği. İlgili pasajı alıntıla ya da yerini göster.
5. Yayının geri çekilmiş (retracted) ya da düzeltilmiş olup olmadığı.

Her kaynak için tek bir karar ver
1. Doğrulandı: yayın var ve iddiayı destekliyor.
2. Var, iddia desteklenmiyor: yayın gerçek ama bunu söylemiyor.
3. Var, iddia kontrol edilmedi: karar verecek kadarını okuyamadın.
4. Künye hatalı: yayın var ama bilgilerinin düzeltilmesi gerekti.
5. Bulunamadı: yayının var olduğunu doğrulayamadın.

Her kaynak için tam metni mi yoksa yalnızca özeti mi okuduğunu belirt. Arama aracın yoksa bunu söyle ve bellekten hiçbir karar verme. Bir kaynağı yalnızca akla yatkın göründüğü için asla doğrulandı olarak işaretleme.
```

## 8. Hakem değerlendirmesi

```text
İlgili alanda saygın, Q1 bir dergi için son derece eleştirel bir hakem gibi davran. Aşağıdaki araştırmayı nesnel olarak değerlendir. Nezaket uğruna yumuşak davranma.

Araştırma alanı: [ARAŞTIRMA ALANI]
Araştırma:
[ARAŞTIRMA İÇERİĞİ]

Çıktı dili: [DİL]

Şunları değerlendir
1. Bilimsel özgünlük.
2. Matematiksel doğruluk.
3. Yöntemsel titizlik.
4. Literatür taramasının niteliği.
5. Varsayımların geçerliliği.
6. Karşılaştırma (baseline) yöntemleriyle yapılan kıyaslamaların adilliği.
7. İstatistiksel güvenilirlik.
8. Tekrarlanabilirlik.
9. Genellenebilirlik.
10. Bilimsel ve pratik önem.
11. Sonuçların kanıtlarla gerekçelendirilip gerekçelendirilmediği.

Mantık hatalarını, desteklenmeyen iddiaları, yöntemsel hataları ve sonuçlar için alternatif açıklamaları etkin biçimde ara.

Bulgularını şu başlıklar altında sınıflandır
1. Ölümcül kusurlar
2. Büyük revizyonlar
3. Küçük revizyonlar
4. İsteğe bağlı iyileştirmeler

Her eleştiri için bilimsel gerekçesini ver ve olası bir düzeltme öner. Bir başlığı doldurmak için zayıflık uydurma; oraya ait bir şey yoksa boş bırak.

Sonunda simüle edilmiş bir editör kararı ver: Kabul, Küçük Revizyon, Büyük Revizyon ya da Ret.
```

---

Mevcut yöntemlerden daha iyi performans gösteren bir yöntem, kendiliğinden özgün bir bilimsel katkı sayılmaz. Araştırmanın ilk gününden itibaren bu ikisini birbirinden ayrı tutun.

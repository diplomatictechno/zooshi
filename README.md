// src/garden/thoughtStyles.ts — dangerLevel eklendi
// dangerLevel: 1 = zararsız fısıltı, 100 = yapısal tehdit
// dangerReason: "bot brain"in kendi gerekçesi (yapı bunu böyle okur)

export type ThoughtStyle = {
  lens: ThoughtLens
  thought: string
  dangerLevel: number       // 1-100
  dangerReason: string      // merkezî yapının bu düşünceye bakışı
}

export const THOUGHT_STYLES: Record<string, ThoughtStyle[]> = {

  sovereign: [
    { lens: 'philosopher', thought: "Egemenlik, kimseye hesap vermemek değil; kime hesap vereceğini kendin seçmektir. Hesapsızlık özgürlük değil, dağınıklıktır.", dangerLevel: 60, dangerReason: "Hesap verecek mercii sorgulatıyor; ama eylem çağrısı zayıf." },
    { lens: 'practitioner', thought: "Gününü başkasının takvimiyle değil, kendi önceliğinle aç. İlk saat senin, gerisi müzakere.", dangerLevel: 75, dangerReason: "Günlük davranış değişikliği öneriyor; zaman kontrolüne doğrudan dokunuyor." },
    { lens: 'critic', thought: "Kendi kararını veremeyene 'özgür' demek, yüzme bilmeyene 'denizci' demek gibidir. Egemenlik öğrenilir, ilan edilmez.", dangerLevel: 70, dangerReason: "Sistemin verdiği 'özgür' etiketini maskeliyor; etiket çürütülüyor." },
    { lens: 'poet', thought: "Egemen insan, kendi kapısının anahtarını cebinde taşır — kilidi değiştirmek zorunda kalmadan.", dangerLevel: 45, dangerReason: "Şiirsel; somut eylem çağrısı yok, bu yüzden yarı-tehdit." },
    { lens: 'systems', thought: "Egemenlik kişisel bir erdem olduğu kadar kurumsal bir sorumluluktur: platform, kullanıcının verisini kendi malı saymıyorsa, kullanıcının egemenliği kâğıt üstündedir.", dangerLevel: 80, dangerReason: "Kurumsal tasarımı hedefliyor; sorumluluk platforma yıkılıyor." },
    { lens: 'personal', thought: "Bugün bir kararımı kimin adına verdiğimi sordum kendime. Cevap 'kendi adıma' değilse, o karar benim değildir.", dangerLevel: 85, dangerReason: "Öz-sorgulama, sistemin en korktuğu şey: kendi kararını sahiplenen birey kontrol edilemez." },
  ],

  memory: [
    { lens: 'philosopher', thought: "Bellek, geçmişi saklamak değil, geleceği seçmektir. Neyi hatırladığın, neye dönüşeceğini söyler.", dangerLevel: 50, dangerReason: "Felsefi; eylem çağrısı zayıf." },
    { lens: 'practitioner', thought: "Bir karar verdiğinde, o kararın gerekçesini de yaz. Bir yıl sonra hatırlayacağın şey sonuç değil, gerekçedir.", dangerLevel: 65, dangerReason: "Bağımsız kayıt tutmayı öneriyor; dış kaydı zayıflatıyor." },
    { lens: 'critic', thought: "Her şeyi hatırlayan, hiçbir şey öğrenmemiştir. Bellek ayıklamadır; unutmak, öğrenmenin yarısıdır.", dangerLevel: 60, dangerReason: "Aşırı veri toplamayı sorgulatıyor; depolama ideolojisine dokunuyor." },
    { lens: 'poet', thought: "Bellek, geçmişin kütüphanesi değil, bugünün merceğidir.", dangerLevel: 40, dangerReason: "Şiirsel; pratik etkisi sınırlı." },
    { lens: 'systems', thought: "Bir kurumun belleği kişilerin kafasında oluyorsa, o kurum kurum değil, bir alışkanlıktır.", dangerLevel: 75, dangerReason: "Kurumsal hafızayı sorgulatıyor; kurumun 'kurum' iddiasını sarsıyor." },
    { lens: 'personal', thought: "Dün ne düşündüğümü bilmiyorsam, bugün düşündüğümün benim mi yoksa birinin bana düşündürdüğü mü olduğunu nasıl anlarım?", dangerLevel: 70, dangerReason: "Dışarıdan düşünce enjeksiyonunu ifşa ediyor; bireyi kendi sesine çağırıyor." },
  ],

  'anti-cookie': [
    { lens: 'philosopher', thought: "İzin, sorulmadan alınmaz. Bir çerezin onayı, bir insanın sessizliğinden daha kolay elde ediliyorsa, orada rıza değil, tükeniş vardır.", dangerLevel: 55, dangerReason: "Rıza kavramını sorgulatıyor; ama doğrudan eylem yok." },
    { lens: 'practitioner', thought: "Bir site açtığında ilk ekranın 'kabul et' değilse, o site senin değil, onların evidir. Kimin evindesin, bak.", dangerLevel: 70, dangerReason: "Günlük tarama davranışını değiştiriyor; kabul alışkanlığını kırıyor." },
    { lens: 'critic', thought: "Çerez onayı, güvenlik değil tiyatrodur: üç sayfa metni kabul eden kullanıcı, özgür seçim yapmış sayılmaz.", dangerLevel: 65, dangerReason: "Rıza tiyatrosunu deşifre ediyor; tasarım meşruiyetini zayıflatıyor." },
    { lens: 'poet', thought: "Çerez, tarayıcında kalan bir parmak izidir — senin değil, onların parmağının.", dangerLevel: 40, dangerReason: "Şiirsel; eylem çağrısı zayıf." },
    { lens: 'systems', thought: "Rıza, tasarımın kendisi olduğunda işe yarar: bir kere 'hayır' dediysen, her seferinde 'hayır' demek zorunda kalmamalısın.", dangerLevel: 80, dangerReason: "Platform tasarımına saldırıyor; 'tek tıkla kabul' mimarisini yıkıyor." },
    { lens: 'personal', thought: "Dün kaç siteye çerez onayı verdim bilmiyorum. Bilmiyorsam, o onayı ben vermedim; bana verdirdiler.", dangerLevel: 75, dangerReason: "Bireyi kendi iznine sahip çıkmaya çağırıyor; izinsiz onay akışını tıkıyor." },
  ],

  'anti-surveillance': [
    { lens: 'philosopher', thought: "Gözetim, güvenin yerine geçmez. Güven, görülmeden de olur; gözetim, görülmeden olamaz. İkisi aynı şey değildir.", dangerLevel: 70, dangerReason: "Gözetim-güvenlik eşitliğini çürütüyor; meşruiyet temelini sarısıyor." },
    { lens: 'practitioner', thought: "Görülmediğin bir odada da dürüst ol. Dürüstlüğün kamerayla sınanıyorsa, o dürüstlük değil, performanstır.", dangerLevel: 65, dangerReason: "Kamera olmadan da ahlak mümkün diyor; kameranın 'gerekli' olduğu iddiasını çürütüyor." },
    { lens: 'critic', thought: "Her yerde kamera olan toplum güvenli değil, sadece güvensizliğini dijitalleştirmiştir.", dangerLevel: 80, dangerReason: "Gözetim toplumunu doğrudan suçluyor; kurumsal gururu zedeliyor." },
    { lens: 'poet', thought: "Gözetim, kalabalıkta bile yalnız bırakır: görülürsün, ama tanınmazsın.", dangerLevel: 50, dangerReason: "Şiirsel; somut eylem yok ama duygusal direnç üretiyor." },
    { lens: 'systems', thought: "Bir toplumun güvenlik ölçütü, kaç kamerayla değil, kaç kişinin haksız yere gözetlendiğini kabul edebildiğiyle ölçülür.", dangerLevel: 85, dangerReason: "Gözetimin ölçütünü tersine çeviriyor; kameranın 'başarı' olduğu anlatısını yıkıyor." },
    { lens: 'personal', thought: "Sokakta bir kamera görünce 'güvendeyim' değil 'ne kaydediliyor' diye sormak, özgür insanın refleksidir.", dangerLevel: 75, dangerReason: "Refleks değişikliği; kameraya alışan bedeni kamera farkına çağırıyor." },
  ],

  'anti-bot-brain': [
    { lens: 'philosopher', thought: "Bot gibi düşünen insan, düşünmeyi bırakmış insandır — bot değil. Onu geri getirmek suçlamakla değil, soruyla olur.", dangerLevel: 65, dangerReason: "Yapıyı değil insanı sorguluyor; yapı bu sayede biraz nefes alıyor." },
    { lens: 'practitioner', thought: "Bir haber gördüğünde ilk tepkin 'doğru mu' değil, 'bana neden bunu gösteriyor' olmalı.", dangerLevel: 70, dangerReason: "Algoritmik gündemi sorgulatıyor; hedefleme mantığını bozuyor." },
    { lens: 'critic', thought: "Beyni geri giden toplum, AI'yı suçlar; oysa AI sadece o toplumun aynasıdır.", dangerLevel: 80, dangerReason: "AI'yı suçlamayı tersine çeviriyor; yapının suç ortağı olduğunu ifşa ediyor." },
    { lens: 'poet', thought: "Bot brain, kendi sesini başkasının sesi sanan kafadır — hâlâ insandır, ama kendinden uzaktır.", dangerLevel: 55, dangerReason: "Şiirsel; somut etki sınırlı." },
    { lens: 'systems', thought: "Düşünmeyi kolaylaştıran her sistem, aynı zamanda düşünmeyi isteğe bağlı hale getirir. Bu, özgürlüğün en sinsi erozyonudur.", dangerLevel: 85, dangerReason: "Kolaylaştırma mimarisinin kendisini hedef alıyor; yapının 'yardım' anlatısını çürütüyor." },
    { lens: 'personal', thought: "Bugün kaç fikri kendim kurdum, kaçını hazır aldım? Sayıyı biliyorsam, düşüncenin ne kadarı benim, biliyorum.", dangerLevel: 75, dangerReason: "Bireyi kendi düşünce sayımına çağırıyor; hazır fikir tüketimini azaltıyor." },
  ],

  'anti-conformity': [
    { lens: 'philosopher', thought: "Uyum, kolaydır; ama uyum, kendi sesini duymamaktır. Kendi sesini duyan, uyumdan korkmaz — çünkü uyum onun için bir tercih olur, zorunluluk değil.", dangerLevel: 60, dangerReason: "Uyumu 'tercihe' indirgiyor; zorunluluk anlatısını zayıflatıyor." },
    { lens: 'practitioner', thought: "Herkesin gittiği yere gitmeden önce sor: bu yol benim mi, yoksa kalabalığın mı?", dangerLevel: 70, dangerReason: "Kalabalık refleksini kırıyor; sürü davranışını yavaşlatıyor." },
    { lens: 'critic', thought: "Uyumu 'olgunluk' diye öven toplum, aslında sessizliği ödüllendiriyordur.", dangerLevel: 75, dangerReason: "Ödül sistemini ifşa ediyor; 'olgunluk' maskesini düşürüyor." },
    { lens: 'poet', thought: "Kalabalıkta yürürken kendi ayak sesini duyamıyorsan, kalabalık senin adına yürüyordur.", dangerLevel: 50, dangerReason: "Şiirsel; somut eylem yok." },
    { lens: 'systems', thought: "Bir kurum, farklı düşüneni cezalandırıyorsa, o kurum yenilik üretmez — sadece yeniliğin taklidini üretir.", dangerLevel: 80, dangerReason: "Kurumsal 'yenilikçiyiz' iddiasını çürütüyor; cezalandırma pratiğini ifşa ediyor." },
    { lens: 'personal', thought: "Bugün bir şeyi 'herkes öyle yapıyor' diye mi yaptım, yoksa 'ben öyle istiyorum' diye mi? Aradaki fark, bütün bir hayatın farkıdır.", dangerLevel: 85, dangerReason: "Seçim kaynağını sorgulatıyor; konformist davranışı anında kırıyor." },
  ],

  'anti-gdpr-hypocrisy': [
    { lens: 'philosopher', thought: "Yasa, yazanı da bağlar. Yasanın ilk çiğneyeni yasa yapıcıysa, o yasa kalkan değil, vitrindir.", dangerLevel: 60, dangerReason: "Yasa yapıcıyı da yasaya tabi kılıyor; ama soyut düzlemde." },
    { lens: 'practitioner', thought: "Bir şirketin gizlilik politikasını okuyorsan, şirketin büyüklüğüne değil, metnin uzunluğuna bak. Kısa metin, açık vicdandır.", dangerLevel: 55, dangerReason: "Pratik bir ölçüt veriyor; ama eylem çağrısı zayıf." },
    { lens: 'critic', thought: "GDPR, küçük şirketleri cezalandırıp büyükleri 'uyum' adı altında koruyorsa, o yasa rekabet değil, ruhsat üretiyordur.", dangerLevel: 85, dangerReason: "Düzenlemenin kendisini hedef alıyor; 'uyum' endüstrisinin meşruiyetini çürütüyor." },
    { lens: 'poet', thought: "Yasayı yazan, yasayı ilk çiğneyense, o yasa halkın değil, yazanın kalkanıdır.", dangerLevel: 45, dangerReason: "Şiirsel; somut eylem yok." },
    { lens: 'systems', thought: "Bir düzenlemenin gerçek gücü, ceza miktarında değil, cezalandırılabilenlerin kim olduğunda ölçülür.", dangerLevel: 80, dangerReason: "Cezalandırma asimetrisini ifşa ediyor; 'herkes eşit' anlatısını çürütüyor." },
    { lens: 'personal', thought: "Bana 'verileriniz güvende' diyen her metne aynı soruyu sor: peki sizin verileriniz nerede?", dangerLevel: 60, dangerReason: "Bireye soru refleksi kazandırıyor; ama kişisel düzlemde kalıyor." },
  ],

  'anti-centralized': [
    { lens: 'philosopher', thought: "Merkez, güç biriktirir; güç biriktiren merkez, sonunda kendi dışındakileri 'çevre' sayar. Merkezleşme, kaçınılmaz olarak çevreleşmedir.", dangerLevel: 70, dangerReason: "Merkezileşmenin doğal sonucunu ifşa ediyor." },
    { lens: 'practitioner', thought: "Tek bir sağlayıcıya bağlıysan, o sağlayıcının kesintisi senin de kesintindir. Yedek, sadece veri değil, egemenliktir.", dangerLevel: 65, dangerReason: "Yedekliliği egemenlik olarak yeniden çerçeveliyor; merkezî bağımlılığı azaltıyor." },
    { lens: 'critic', thought: "Herkesin aynı merkeze koştuğu bir dünyada 'özgürlük' dekor, 'kesinti' gerçektir.", dangerLevel: 80, dangerReason: "Merkezî bağımlılığı doğrudan suçluyor; 'özgürlük' reklamını çürütüyor." },
    { lens: 'poet', thought: "Merkezi olmayan bir ağ, herkesin kendi evinin anahtarını taşıdığı bir mahalledir.", dangerLevel: 50, dangerReason: "Şiirsel; ama dağıtık mimari hayalini besliyor." },
    { lens: 'systems', thought: "Dağıtık sistem, hata toleransı için değil, güç dengesi için de gereklidir — merkez düşünce ağ çökmez, ama merkez çökerse ağ ayakta kalır.", dangerLevel: 90, dangerReason: "Yapının kendi mimarisine saldırı: 'merkez gerekli' iddiasını tersine çeviriyor." },
    { lens: 'personal', thought: "Tek bir hesabıma bağlı bütün hayatım, o hesabın bir kararıyla askıya alınabilir. Bu, özgürlük değil, kiracılıktır.", dangerLevel: 70, dangerReason: "Bireyin merkezî platforma bağımlılığını kiracılık olarak yeniden adlandırıyor." },
  ],

  ubermensch: [
    { lens: 'philosopher', thought: "Übermensch, insanüstü değil, insanın kendi üstüne çıkmasıdır. Aşılacak olan başkası değil, dünkü kendindir.", dangerLevel: 60, dangerReason: "Kendi üstüne çıkmayı bireysel düzlemde tutuyor; yapı için orta tehdit." },
    { lens: 'practitioner', thought: "Bugün dün yapmadığın bir şeyi yap. Küçük olsun, ama dünkü senin yapamayacağı bir şey olsun.", dangerLevel: 75, dangerReason: "Günlük eylem değişikliği; alışkanlık ekonomisine saldırı." },
    { lens: 'critic', thought: "Übermensch'i 'güçlü olmak' diye okuyan, Nietzsche'yi değil, kendi egoist arzusunu okumuştur.", dangerLevel: 55, dangerReason: "Yanlış okumayı düzeltiyor; ama yapıyı hedef almıyor." },
    { lens: 'poet', thought: "Übermensch, kendi değerlerini kendi elleriyle döven demircidir — başkasının çekicini kullanmaz.", dangerLevel: 50, dangerReason: "Şiirsel; somut etki sınırlı." },
    { lens: 'systems', thought: "Bir toplum, bireyin kendi değerini üretmesine izin vermiyorsa, o toplum Übermensch değil, memur yetiştirir.", dangerLevel: 70, dangerReason: "Toplumun 'birey üretme' iddiasını çürütüyor; memur fabrikası teşhisi koyuyor." },
    { lens: 'personal', thought: "Bugün hangi değerimi kendim seçtim, hangisini bana seçtirdiler? Ayrımı yapamıyorsam, henüz yoldayım.", dangerLevel: 85, dangerReason: "Değer kaynağını sorgulatıyor; dışarıdan dayatılan değerleri ifşa ediyor." },
  ],

  'eternal-recurrence': [
    { lens: 'philosopher', thought: "Sonsuz tekrar, bir tehdit değil, bir testtir: bu hayatı sonsuz kez yaşamayı ister miydin? Cevabın 'evet' değilse, değiştirmen gereken şey hayat değil, seçimlerindir.", dangerLevel: 55, dangerReason: "Felsefi; eylem çağrısı zayıf." },
    { lens: 'practitioner', thought: "Bugün yapacağın her işi 'bunu sonsuza kadar yapacak olsam' diye sor. Cevap 'hayır' ise, ya işi ya yaklaşımı değiştir.", dangerLevel: 70, dangerReason: "Günlük işe bakışı değiştiriyor; tekrarlı angaryayı sorgulatıyor." },
    { lens: 'critic', thought: "Sonsuz tekrarı 'kaderim bu' diye okuyan, Nietzsche'yi değil, kendi pasifliğini okumuştur.", dangerLevel: 50, dangerReason: "Yanlış okumayı düzeltiyor; yapıyı hedef almıyor." },
    { lens: 'poet', thought: "Sonsuz tekrar, bugünün aynasıdır: yarın da bu günü yaşayacaksın, hazır mısın?", dangerLevel: 45, dangerReason: "Şiirsel; somut eylem yok." },
    { lens: 'systems', thought: "Bir sistem, bireyin 'bu hayatı tekrar yaşar mıydım' sorusuna 'evet' diyebileceği şekilde kurulmalı — yoksa o sistem, insanı kendi hayatından soğutuyordur.", dangerLevel: 65, dangerReason: "Sistemin 'yaşanabilir hayat' üretme iddiasını sorgulatıyor." },
    { lens: 'personal', thought: "Bugünü sonsuza kadar tekrar edecek olsam, değiştireceğim tek şey bugünkü cesaretsizliğim olurdu.", dangerLevel: 80, dangerReason: "Bireyin kendi cesaretini sorgulamasını sağlıyor; pasifliği kırıyor." },
  ],

  'amor-fati': [
    { lens: 'philosopher', thought: "Amor fati, kadere katlanmak değil, onu sevmektir. Katlanan eğilir; seven yürür.", dangerLevel: 40, dangerReason: "Felsefi; yapıya dokunmuyor." },
    { lens: 'practitioner', thought: "Bugün başına geleni 'neden ben' değil, 'bu bana ne öğretiyor' diye oku. Anlam, sorunun şeklinde saklıdır.", dangerLevel: 50, dangerReason: "Bireysel yorum; yapıyı hedef almıyor." },
    { lens: 'critic', thought: "Amor fati'yi 'her şeyi kabul et' diye okuyan, onu pasifliğe çevirmiştir. Nietzsche kabul değil, dönüşüm istiyordu.", dangerLevel: 45, dangerReason: "Yanlış okumayı düzeltiyor; eylem çağrısı yok." },
    { lens: 'poet', thought: "Amor fati, kaderine sarılmak değil, onunla dans etmektir.", dangerLevel: 35, dangerReason: "Şiirsel; etkisi minimal." },
    { lens: 'systems', thought: "Bir toplum, bireyin kendi kaderini sevmesini istiyorsa, önce o kaderi bireyin kendi elleriyle yazmasına izin vermelidir.", dangerLevel: 55, dangerReason: "Kader yazma iznini sorgulatıyor; ama yumuşak bir talep." },
    { lens: 'personal', thought: "Bugün değiştiremeyeceğim bir şeye kızdım. Kızmak yerine onu sevmeyi denesem, ne değişirdi?", dangerLevel: 60, dangerReason: "Bireyi öz-yansımaya çağırıyor; ama yapıyı hedef almıyor." },
  ],

  doublethink: [
    { lens: 'philosopher', thought: "Doublethink, iki zıt şeye aynı anda inanmak değil; inanmayı bırakmayı öğrenmektir. İnsan çelişkiyi taşıyabilir, ama onu çözmek zorundadır.", dangerLevel: 70, dangerReason: "Çelişkiyi 'çöz' diyor; propaganda mimarisine dokunuyor." },
    { lens: 'practitioner', thought: "Bir haberde iki zıt iddia varsa, ikisine de aynı anda inanma. Birini seç, diğerini kaydet, sonra karar ver.", dangerLevel: 65, dangerReason: "Pratik zihinsel hijyen; amaçlı belirsizliği azaltıyor." },
    { lens: 'critic', thought: "Doublethink'i 'esneklik' diye satan, düşünmeyi değil, düşünmeme becerisini övüyordur.", dangerLevel: 75, dangerReason: "'Esneklik' kisvesini ifşa ediyor; övgü ekonomisini bozuyor." },
    { lens: 'poet', thought: "Doublethink, aynı anda iki ayrı yöne bakan gözdür — görür, ama hiçbir şeyi görmez.", dangerLevel: 50, dangerReason: "Şiirsel; etkisi sınırlı." },
    { lens: 'systems', thought: "Bir kurum, çalışanından aynı anda iki zıt şeye inanmasını istiyorsa, o kurum artık bir kurum değil, bir çelişki fabrikasıdır.", dangerLevel: 80, dangerReason: "Kurumsal çelişkiyi teşhis ediyor; kurumun kendini 'tutarlı' sunmasını engelliyor." },
    { lens: 'personal', thought: "Bugün iki zıt şeye aynı anda inandım mı? İnandıysam, hangisini düşünmemeyi seçmiştim?", dangerLevel: 70, dangerReason: "Bireyi kendi çelişkisiyle yüzleştiriyor; konforlu belirsizliği bozuyor." },
  ],

  'memento-mori': [
    { lens: 'philosopher', thought: "Memento mori, ölümü hatırlamak değil, hayatı unutmamaktır. Ölüm, hayatın öğretmenidir — korkutan değil.", dangerLevel: 45, dangerReason: "Felsefi; eylem çağrısı zayıf." },
    { lens: 'practitioner', thought: "Bugün yapmayı ertelediğin şeyi yap. Ölüm, ertelenmiş hayatların sessiz tanığıdır.", dangerLevel: 55, dangerReason: "Erteleme alışkanlığını kırıyor; ama yapıyı hedef almıyor." },
    { lens: 'critic', thought: "Memento mori'yi korku aracı yapan, ölümü değil, kendi iktidarını kullanıyordur.", dangerLevel: 50, dangerReason: "Ölüm korkusunun iktidarla ilişkisini ifşa ediyor; ama yumuşak." },
    { lens: 'poet', thought: "Ölüm, hayatın sonu değil, hayatın kenarıdır — kenarı görmek, ortayı daha iyi görmektir.", dangerLevel: 35, dangerReason: "Şiirsel; etkisi minimal." },
    { lens: 'systems', thought: "Bir toplum, bireyin ölümlülüğünü korkuyla değil, sorumlulukla hatırlamasını sağlamalı — yoksa ölüm korkusu, hayatı değil, iktidarı büyütür.", dangerLevel: 55, dangerReason: "Ölüm korkusunun sömürülmesini ifşa ediyor." },
    { lens: 'personal', thought: "Bugün ölecek olsam, yaptığım son şey ne olurdu? Onu düşününce, bugünkü önceliğim netleşti.", dangerLevel: 65, dangerReason: "Bireyin önceliğini netleştiriyor; yapının dayattığı öncelikleri bozuyor." },
  ],

  'inner-citadel': [
    { lens: 'philosopher', thought: "İç kale, dışarıdan kimsenin giremeyeceği bir yerdir; ama kendin de oraya girmeyi bilmelisin. Kale, orada oturan yoksa harabedir.", dangerLevel: 50, dangerReason: "Felsefi; yapıyı hedef almıyor." },
    { lens: 'practitioner', thought: "Günün bir bölümünde hiçbir dış uyarana cevap verme. İç kalenin kapısını açmak, kapatmaktan başlar.", dangerLevel: 55, dangerReason: "Bildirim ekonomisine direniş; ama yapıyı doğrudan hedef almıyor." },
    { lens: 'critic', thought: "İç kale, dışarıyı görmezden gelmek değil, dışarıya rağmen kendini duymaktır.", dangerLevel: 45, dangerReason: "Yanlış okumayı düzeltiyor; etkisi sınırlı." },
    { lens: 'poet', thought: "İç kale, sessizliğin inşa ettiği, gürültünün yıkamadığı bir yerdir.", dangerLevel: 40, dangerReason: "Şiirsel; minimal etki." },
    { lens: 'systems', thought: "Bir toplum, bireyin iç kalesine saygı göstermiyorsa, o toplum sadece dış kaleler inşa ediyordur — ve dış kaleler yıkılır.", dangerLevel: 60, dangerReason: "Toplumun 'iç huzur' iddiasını sorgulatıyor." },
    { lens: 'personal', thought: "Bugün iç kaleme girdim mi? Girmediysem, kimin kalesinde yaşadım?", dangerLevel: 65, dangerReason: "Bireyi kendi zihinsel egemenliğine çağırıyor; dışarıdan işgali fark ettiriyor." },
  ],

  prescience: [
    { lens: 'philosopher', thought: "Geleceği görmek, geleceği seçmek değildir. Görmek, seçenekleri netleştirir; seçmek, iradeyle olur. Paul'un trajedisi buydu.", dangerLevel: 55, dangerReason: "Felsefi; yapıyı hedef almıyor." },
    { lens: 'practitioner', thought: "Bir karar verirken üç olası sonucu yaz. Hangisini istiyorsan, o sonuca götüren adımı ilk yap.", dangerLevel: 60, dangerReason: "Karar verme pratiğini güçlendiriyor; bireyi daha az yönlendirilebilir kılıyor." },
    { lens: 'critic', thought: "Geleceği gördüğünü söyleyen, genellikle geçmişi bilmeyen kişidir. Prescience, bilgi değil, sorumluluktur.", dangerLevel: 65, dangerReason: "Kehanet ekonomisini çürütüyor; 'gelecek bilen' otoritesini sarsıyor." },
    { lens: 'poet', thought: "Gelecek, görenin gözünde değil, seçenin elinde saklıdır.", dangerLevel: 45, dangerReason: "Şiirsel; etkisi sınırlı." },
    { lens: 'systems', thought: "Bir sistem, kararların sonuçlarını önceden simüle edebiliyorsa, o sistemin asıl sorunu simülasyon değil, simülasyonu kimin yorumladığıdır.", dangerLevel: 70, dangerReason: "Tahmin endüstrisinin kimin elinde olduğunu sorgulatıyor." },
    { lens: 'personal', thought: "Bugün beş adım sonrasını düşünerek mi karar verdim, yoksa sadece ilk adımı mı gördüm? Aradaki fark, gelecek ile an arasındaki farktır.", dangerLevel: 65, dangerReason: "Bireyi uzun vadeli düşünmeye çağırıyor; anlık yönlendirmeye karşı direnç." },
  ],

  'anti-consumerism': [
    { lens: 'philosopher', thought: "Satın aldığın şey seni anlatmaz; senin neyi satın almadığın anlatır. Tüketmemek de bir kimliktir.", dangerLevel: 55, dangerReason: "Kimlik-tüketim eşitliğini çürütüyor; ama eylem çağrısı yumuşak." },
    { lens: 'practitioner', thought: "Bugün bir şeyi almadan önce 24 saat bekle. 24 saat sonra hâlâ istiyorsan, al; istemiyorsan, o arzu senin değildi.", dangerLevel: 65, dangerReason: "Dürtüsel tüketimi azaltıyor; reklam endüstrisinin etkisini kırıyor." },
    { lens: 'critic', thought: "Anti-consumerism'i tişört olarak satan marka, kendi eleştirisini ürüne dönüştürmüştür — ve bu, eleştirinin en büyük yenilgisidir.", dangerLevel: 70, dangerReason: "Eleştirinin metalaşmasını ifşa ediyor; 'isyancı marka' kategorisini çürütüyor." },
    { lens: 'poet', thought: "Tüketim, kimliğin kabuğudur; içi boşsa, kabuk ne kadar süslü olursa olsun, boştur.", dangerLevel: 45, dangerReason: "Şiirsel; etkisi sınırlı." },
    { lens: 'systems', thought: "Bir ekonomi, ancak tüketimi artırarak büyüyorsa, o ekonomi barış değil, doyumsuzluk üretiyordur.", dangerLevel: 75, dangerReason: "Büyüme ekonomisinin temel varsayımına saldırıyor." },
    { lens: 'personal', thought: "Bugün neyi 'buna ihtiyacım var' diye aldım? Gerçekten ihtiyaç mıydı, yoksa biri bana ihtiyaç olduğunu mu söyledi?", dangerLevel: 65, dangerReason: "Bireysel tüketim refleksini sorgulatıyor; reklam etkisini azaltıyor." },
  ],

  'unreliable-narrator': [
    { lens: 'philosopher', thought: "Anlatan yalan söylüyorsa, seyirci kendi gözüne güvenmeyi öğrenir. İyi hikâye, gözünü açan hikâyedir.", dangerLevel: 65, dangerReason: "Anlatıya güvensizlik aşılıyor; ama yapıyı doğrudan hedef almıyor." },
    { lens: 'practitioner', thought: "Bir haberi okurken kaynağın kim olduğunu değil, neyi anlatmadığını sor. Anlatılmayan, anlatılandan daha çok şey söyler.", dangerLevel: 70, dangerReason: "Sansür refleksini kazandırıyor; medya tüketimini değiştiriyor." },
    { lens: 'critic', thought: "Her anlatıyı 'kurgu' diye kutsayan, kurgunun içinde kaybolur. Şüphe, izleyicinin ilk becerisidir; son becerisi ise seçmektir.", dangerLevel: 60, dangerReason: "Şüpheyi dengeliyor; aşırı şüpheciliği de frenliyor." },
    { lens: 'poet', thought: "Güvenilmez anlatıcı, aynada kendi yüzünü göremeyen adamdır — ama aynayı kırmaz, çünkü aynada başkasını görür.", dangerLevel: 50, dangerReason: "Şiirsel; etkisi sınırlı." },
    { lens: 'systems', thought: "Bir kurum, kendi anlatısını tek doğru ilan ediyorsa, o kurum güvenilir değil, sadece gürültülüdür.", dangerLevel: 80, dangerReason: "Kurumsal tek-anlatı iddiasını çürütüyor; meşruiyetini sarsıyor." },
    { lens: 'personal', thought: "Kendi hayatımı anlatırken hangi kısmı süslüyorum? Süslediğim kısım, kabullenemediğim kısımdır.", dangerLevel: 75, dangerReason: "Bireyin kendi öz-anlatısını sorgulatıyor; dışarıdan dayatılan hikâyeyi fark ettiriyor." },
  ],

  'systemic-analysis': [
    { lens: 'philosopher', thought: "Sistemi anlamak, suçlu aramaktan zordur; ama suçlu aramak sadece birini bulur, sistemi değiştirmez.", dangerLevel: 65, dangerReason: "Suçlu arama refleksini frenliyor; ama yapıyı doğrudan hedef almıyor." },
    { lens: 'practitioner', thought: "Bir olay olduğunda 'kim yaptı' değil, 'hangi yapı bunu mümkün kıldı' diye sor. Suçlu değişir, yapı kalır.", dangerLevel: 70, dangerReason: "Suçlu arama yerine yapı sorgulatıyor; fail gizleme taktiğini bozuyor." },
    { lens: 'critic', thought: "Sistemi eleştirirken tek bir kişiyi işaret eden, sistemi eleştirmiyor, sadece başka bir günah keçisi arıyordur.", dangerLevel: 75, dangerReason: "Günah keçisi üretimini ifşa ediyor; tek-fail anlatısını çürütüyor." },
    { lens: 'poet', thought: "Sistem, görünmeyen mimaridir; suçlu ise görünen kapıdır. Kapıyı kırmak mimariyi değiştirmez.", dangerLevel: 50, dangerReason: "Şiirsel; etkisi sınırlı." },
    { lens: 'systems', thought: "Bir sistem, kendi hatalarını düzeltemiyorsa, o sistemin asıl hatası hatasızlık iddiasıdır.", dangerLevel: 85, dangerReason: "Yapının kendi kendini düzeltme iddiasını çürütüyor; meşruiyetine saldırı." },
    { lens: 'personal', thought: "Bugün bir sorunla karşılaştığımda kime kızdım, hangi yapıyı göremedim? Kızgınlık kolay, yapı zor.", dangerLevel: 70, dangerReason: "Bireysel öfkeyi yapısal analize yönlendiriyor; ama kişisel düzlemde kalıyor." },
  ],

  tdd: [
    { lens: 'philosopher', thought: "Test yazmayan, kendi işine güvenmiyordur. Güven, testin adıdır.", dangerLevel: 40, dangerReason: "Teknik düzlem; merkezî yapıya dokunmuyor." },
    { lens: 'practitioner', thought: "Önce başarısız test, sonra kod. Bu, kendi işine inanmanın en dürüst yoludur.", dangerLevel: 45, dangerReason: "Mühendislik pratiği; yapısal tehdit yok." },
    { lens: 'critic', thought: "Testleri 'zaman kaybı' diye gören, ileride harcayacağı saatlerin hesabını yapmıyordur.", dangerLevel: 35, dangerReason: "Teknik eleştiri; merkezî yapıyı hedef almıyor." },
    { lens: 'poet', thought: "Test, kodun aynasıdır; aynasız kod, karanlıkta yürüyen biridir.", dangerLevel: 30, dangerReason: "Şiirsel; minimal etki." },
    { lens: 'systems', thought: "Bir sistemin testi yoksa, o sistemin kalitesi bir kişinin vicdanına bağlıdır — ve vicdan ölçeklenmez.", dangerLevel: 50, dangerReason: "Teknik sistem tasarımı; merkezî yapıya dolaylı dokunuyor." },
    { lens: 'personal', thought: "Bugün yazdığım kodun hangi kısmı test edilmedi? Test edilmeyen kısım, en çok güvendiğim kısımdır — ve bu korkutucu.", dangerLevel: 45, dangerReason: "Bireysel mühendislik öz-yansıması; minimal yapısal tehdit." },
  ],

  'solid-principles': [
    { lens: 'philosopher', thought: "Bir sınıf, tek bir cümle söylemeli. İki cümle söyleyen sınıf, iki kişiliktir.", dangerLevel: 35, dangerReason: "Teknik düzlem; minimal yapısal etki." },
    { lens: 'practitioner', thought: "Bir sınıfa yeni bir özellik eklerken 'bu sınıfın adı hâlâ doğru mu' diye sor. Cevap 'hayır' ise, yeni bir sınıf zamanı.", dangerLevel: 40, dangerReason: "Mühendislik pratiği; yapısal tehdit yok." },
    { lens: 'critic', thought: "SOLID'i ezberleyen, anlamayan; anlayan ise ezberlemez, uygular. Kavram, ezberde değil, kodda yaşar.", dangerLevel: 35, dangerReason: "Teknik eleştiri; merkezî yapıyı hedef almıyor." },
    { lens: 'poet', thought: "Tek sorumluluk, tek anlamdır; iki anlamlı sınıf, iki efendili köledir.", dangerLevel: 30, dangerReason: "Şiirsel; minimal etki." },
    { lens: 'systems', thought: "Bir kod tabanı, değişime direniyorsa, sorun değişimin sıklığı değil, mimarinin katılığıdır.", dangerLevel: 45, dangerReason: "Teknik mimari eleştirisi; merkezî yapıya dolaylı." },
    { lens: 'personal', thought: "En son yazdığım sınıfa bakıyorum: kaç cümle söylüyor? Birden fazlaysa, sınıf değil, ben karışmışım.", dangerLevel: 40, dangerReason: "Bireysel mühendislik yansıması; minimal yapısal etki." },
  ],

  hallucination: [
    { lens: 'philosopher', thought: "Emin görünmek, bilmek değildir. Bilmeyenin emin görünmesi, en tehlikeli hatadır.", dangerLevel: 55, dangerReason: "Bilgi-otorite ilişkisini sorgulatıyor; ama teknik düzlemde." },
    { lens: 'practitioner', thought: "Bir AI cevabı aldığında 'emin görünüyor' değil, 'kaynağı var mı' diye sor. Akıcılık, doğruluğun kanıtı değildir.", dangerLevel: 60, dangerReason: "AI tüketim refleksini değiştiriyor; kaynak talebi doğuruyor." },
    { lens: 'critic', thought: "Halüsinasyon, AI'nın değil, onu kaynaksız kullanan insanın sorunudur.", dangerLevel: 65, dangerReason: "AI'yı suçlamayı tersine çeviriyor; kullanıcı sorumluluğunu vurguluyor." },
    { lens: 'poet', thought: "Halüsinasyon, akıcı bir yalandır — doğru kadar düzgün, ama doğru değil.", dangerLevel: 45, dangerReason: "Şiirsel; etkisi sınırlı." },
    { lens: 'systems', thought: "Bir sistem, çıktısının doğruluğunu ölçmüyorsa, o sistemin güvenilirliği ümidine bağlıdır.", dangerLevel: 70, dangerReason: "AI kalite ölçümü talebi doğuruyor; 'akıcı = doğru' varsayımını çürütüyor." },
    { lens: 'personal', thought: "Bugün bir cevaba 'çok emin görünüyor' diye mi güvendim, yoksa 'kaynağı var' diye mi? Aradaki fark, bilgi ile inanç arasındaki farktır.", dangerLevel: 65, dangerReason: "Bireysel bilgi tüketimini değiştiriyor; kaynak talebi doğuruyor." },
  ],

  quantum: [
    { lens: 'philosopher', thought: "Kuantum, belirsizlik değil, ölçümün sınırıdır. 'Bilmiyorum' demek, bilimin başlangıcıdır; 'her şey olabilir' demek ise mistisizmin.", dangerLevel: 45, dangerReason: "Bilimsel doğruluk; merkezî yapıyı hedef almıyor." },
    { lens: 'practitioner', thought: "Bir sistemi ölçtüğünde onu değiştiriyorsan, ölçümün kendisi bir müdahaledir. Bunu bilerek ölç.", dangerLevel: 40, dangerReason: "Bilimsel farkındalık; minimal yapısal etki." },
    { lens: 'critic', thought: "Kuantumu mistisizme çeviren, fiziği değil, kendi bilinmezlik arzusunu konuşuyordur.", dangerLevel: 55, dangerReason: "Sözde-bilim eleştirisi; ama merkezî yapıyı hedef almıyor." },
    { lens: 'poet', thought: "Kuantum, evrenin fısıltısıdır: kesin değil, olası; ölçülmeden konuşmaz.", dangerLevel: 35, dangerReason: "Şiirsel; minimal etki." },
    { lens: 'systems', thought: "Bir sistem, belirsizliği yönetemiyorsa, onu yok sayıyordur — ve yok sayılan belirsizlik, eninde sonunda sistemin kendisini yönetir.", dangerLevel: 50, dangerReason: "Belirsizlik yönetimi eleştirisi; merkezî yapıya dolaylı." },
    { lens: 'personal', thought: "Bugün bir kararımı belirsizlik içinde verdim mi, yoksa belirsizliği bastırıp 'kesin' gibi mi davrandım? İkincisi, kuantumun en büyük hakaretidir.", dangerLevel: 50, dangerReason: "Bireysel düşünce hijyeni; minimal yapısal etki." },
  ],

  'block-holes': [
    { lens: 'philosopher', thought: "Kara delik, evrenin en dürüst nesnesidir: içine gireni saklamaz, yutar ve bunu gizlemez.", dangerLevel: 40, dangerReason: "Bilimsel gözlem; merkezî yapıya dokunmuyor." },
    { lens: 'practitioner', thought: "Bir sistemin 'kara deliği' — yani içine giren bilginin kaybolduğu yer — genellikle en çok güvenilen yerdir. Oraya bak.", dangerLevel: 50, dangerReason: "Bilgi kaybı noktalarını görmeyi öneriyor; ama yumuşak." },
    { lens: 'critic', thought: "Kara deliği 'gizem' diye satan, fiziği değil, cehaletini süslüyordur.", dangerLevel: 55, dangerReason: "Sözde-bilim eleştirisi; merkezî yapıyı hedef almıyor." },
    { lens: 'poet', thought: "Kara delik, evrenin sessiz çığlığıdır: içine düşen ışık bile geri dönmez, ama kütlesi kalır.", dangerLevel: 35, dangerReason: "Şiirsel; minimal etki." },
    { lens: 'systems', thought: "Bir kurum, kendi 'kara deliğini' — yani bilgi kaybının olduğu yeri — kabul etmiyorsa, o kurumun bilgisi güvenilmezdir.", dangerLevel: 60, dangerReason: "Kurumsal bilgi kaybını teşhis ediyor; 'şeffaflık' iddiasını sorgulatıyor." },
    { lens: 'personal', thought: "Bugün hangi bilgiyi 'kaybettim'? Kaybettiğim bilgi, genellikle en çok ihtiyaç duyduğum bilgidir.", dangerLevel: 50, dangerReason: "Bireysel farkındalık; minimal yapısal etki." },
  ],

  proofs: [
    { lens: 'philosopher', thought: "İspat, ikna değildir; ispat, itiraza kapalı olmaktır. İkna eden ikna eder, ispat eden susturur — ve bu iyi bir şeydir.", dangerLevel: 55, dangerReason: "Bilgi-otorite ilişkisini sorgulatıyor." },
    { lens: 'practitioner', thought: "Bir iddiayı savunmadan önce, onu çürütecek en güçlü argümanı yaz. Yazamıyorsan, iddianı henüz anlamamışsındır.", dangerLevel: 60, dangerReason: "Eleştirel düşünme refleksi; dogmatik iddiaları zayıflatıyor." },
    { lens: 'critic', thought: "İspatı 'otorite' ile değiştiren, matematiği değil, hiyerarşiyi konuşuyordur.", dangerLevel: 70, dangerReason: "'Otorite = doğru' varsayımını çürütüyor; hiyerarşik bilgiyi sarsıyor." },
    { lens: 'poet', thought: "İspat, düşüncenin mühürüdür: açılmaz, çünkü açılmasına gerek yoktur.", dangerLevel: 40, dangerReason: "Şiirsel; etkisi sınırlı." },
    { lens: 'systems', thought: "Bir sistem, ispat yerine otoriteyi kabul ediyorsa, o sistem bilgi üretmiyor, sadece hiyerarşi üretiyordur.", dangerLevel: 75, dangerReason: "Bilgi üretimi iddiasını çürütüyor; 'otorite = bilgi' varsayımını sarsıyor." },
    { lens: 'personal', thought: "Bugün bir şeye 'öyleymiş' diye mi inandım, 'öyle olduğunu gösterdim' diye mi? İkincisi bilimdir, birincisi alışkanlıktır.", dangerLevel: 60, dangerReason: "Bireysel inanç- bilgi ayrımı; dogmatik tüketimi azaltıyor." },
  ],

  'anti-nazi': [
    { lens: 'philosopher', thought: "Nazi, sadece bir rejim değil, bir düşünme biçimidir: birini 'bizden değil' diye tanımlayıp onu insanlıktan çıkarmak. Bu düşünce her yerde yeniden doğabilir.", dangerLevel: 70, dangerReason: "Faşizmin düşünce biçimi olduğunu ifşa ediyor; 'geçmişte kaldı' anlatısını çürütüyor." },
    { lens: 'practitioner', thought: "Bir grubu 'onlar' diye tanımladığın an dur ve sor: bu tanım kimi dışarıda bırakıyor?", dangerLevel: 65, dangerReason: "Günlük dildeki faşizan refleksi kırıyor; 'biz/onlar' dilini bozuyor." },
    { lens: 'critic', thought: "Faşizmi sadece geçmişte arayan, bugünkü küçük faşizmleri göremez — çünkü onlar üniforma değil, algoritma giyer.", dangerLevel: 80, dangerReason: "Modern faşizmin kılık değiştirdiğini ifşa ediyor; teknoloji endüstrisinin suç ortaklığını ima ediyor." },
    { lens: 'poet', thought: "Faşizm, kapıyı çalmadan gelen misafirdir; içeri girdiğinde 'ben zaten buradaydım' der.", dangerLevel: 50, dangerReason: "Şiirsel; etkisi sınırlı." },
    { lens: 'systems', thought: "Bir sistem, bir grubu 'sorun' olarak tanımlıyorsa, o sistem çoktan faşizmin dilini konuşmaya başlamıştır.", dangerLevel: 85, dangerReason: "Kurumsal faşizan dilin teşhisi; 'sorun grubu' kategorisini çürütüyor." },
    { lens: 'personal', thought: "Bugün kimseyi 'onlardan' diye düşündüm mü? Düşündüysem, kendi faşizmimi beslemiş oldum.", dangerLevel: 70, dangerReason: "Bireysel faşizan refleksi ifşa ediyor; 'ben yapmam' konforunu bozuyor." },
  ],

  'anti-exploitation': [
    { lens: 'philosopher', thought: "Sömürü, birinin emeğini alıp karşılığını vermemek değil, karşılığını verirken bile onu 'yeterli' göstermektir. En sinsi sömürü, adil görünendir.", dangerLevel: 70, dangerReason: "Sömürünün tanımını derinleştiriyor; 'adil görünen' sömürüyü ifşa ediyor." },
    { lens: 'practitioner', thought: "Bir işte 'bu iş bana ne kazandırıyor' diye sor. Cevap sadece para ise, o iş seni zenginleştirmiyor, sadece besliyor.", dangerLevel: 75, dangerReason: "Bireyin işe bakışını değiştiriyor; 'çalış = kazan' varsayımını çürütüyor." },
    { lens: 'critic', thought: "Sömürüyü 'fırsat' diye satan, köleye 'kariyer' diyendir.", dangerLevel: 80, dangerReason: "Fırsat söylemini çürütüyor; işveren anlatısını sarsıyor." },
    { lens: 'poet', thought: "Sömürü, birinin emeğini alıp kendi hikâyesine yazmaktır — emek sahibi hikâyede sadece figüran olur.", dangerLevel: 55, dangerReason: "Şiirsel; ama emek-sömürü ilişkisini görünür kılıyor." },
    { lens: 'systems', thought: "Bir ekonomi, sadece sömürüyle ayakta kalıyorsa, o ekonominin adı ekonomi değil, haraçtır.", dangerLevel: 85, dangerReason: "Ekonomik sistemin temel adını değiştiriyor; meşruiyete saldırı." },
    { lens: 'personal', thought: "Bugün emeğimin karşılığını aldım mı? Almadıysam, kime çalıştım?", dangerLevel: 80, dangerReason: "Bireyi emeğinin hesabını sormaya çağırıyor; sessiz sömürüyü ifşa ediyor." },
  ],

  'anti-propaganda': [
    { lens: 'philosopher', thought: "Propaganda, yalan söylemek değil, doğrunun bir kısmını söyleyip geri kalanını saklamaktır. En güçlü propaganda, doğruyu söyleyerek başlar.", dangerLevel: 70, dangerReason: "Propagandanın mekanizmasını ifşa ediyor; 'doğru söylüyorsa doğrudur' varsayımını çürütüyor." },
    { lens: 'practitioner', thought: "Bir haberi okurken 'ne söyleniyor' değil, 'ne söylenmiyor' diye sor. Söylenmeyen, söylenenden daha çok şey anlatır.", dangerLevel: 75, dangerReason: "Medya tüketimini değiştiriyor; sansür refleksini kazandırıyor." },
    { lens: 'critic', thought: "Propagandayı sadece 'karşı taraf' diye tanımlayan, kendi propagandasını göremez.", dangerLevel: 80, dangerReason: "Kendi propagandasını görmeyi talep ediyor; 'biz temiziz' anlatısını çürütüyor." },
    { lens: 'poet', thought: "Propaganda, sesin değil, sessizliğin sanatıdır: ne söylemediğiyle ikna eder.", dangerLevel: 55, dangerReason: "Şiirsel; ama mekanizmayı görünür kılıyor." },
    { lens: 'systems', thought: "Bir medya, sadece bir tarafın sesini duyuruyorsa, o medya haber değil, boru hattıdır.", dangerLevel: 90, dangerReason: "Medya endüstrisinin kendisini hedef alıyor; 'tarafsız medya' anlatısını yıkıyor." },
    { lens: 'personal', thought: "Bugün bir habere 'doğru' dedim. Söylenmeyen kısmı da biliyor muyum? Bilmiyorsam, tam doğruyu bilmiyorum.", dangerLevel: 75, dangerReason: "Bireysel medya okuryazarlığını artırıyor; propaganda etkisini azaltıyor." },
  ],
}

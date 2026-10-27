
<div align="center">

# 🍃 Learning Cards

### Arapça Kelime Kartı Oyunu

<p>Google Sheets ve JavaScript ile geliştirilen interaktif kelime öğrenme oyunu.</p>

<a href="https://s4w4t4ri.github.io/learning-cards-like-quizlet/">
<strong>🍃 OYUNU OYNA</strong>
</a>

</div>

---

<h2>🎮 Nasıl Oynanır?</h2>

Bu oyunu, öğrendiğim dilde yeni kelimeleri daha kolay tekrar edebilmek için tasarladım. Arapça kelimeler üzerinden örnek vereceğim:

**1. Kelime seviyesini seç.**

Karışık kelimeler veya A1 gibi çalışmak istediğin kategoriyi seç.

**2. Kart sayısını belirle.**

Seçtiğin kategoriden kaç kelime sorulmasını istediğini gir.

**3. Başla!**

Başla butonuna tıklayarak oyunu başlat.

**4. Kartları çevir ve cevabını kontrol et.**

Kartın üzerine tıklayarak Türkçe karşılığını gör. Ardından kelimeyi bilip bilmediğini işaretle.

**5. Yanlışlarını tekrar et.**

Setin sonunda bilemediğin kelimeler yeniden karşına gelir.

> 💡 **İpucu:** Kart sayısını belirlemek önemli! Bir set tamamlandığında yanlış cevapladığın kelimeler tekrar sorulur. Sayı belirlemezsen seçtiğin kategorideki tüm kelimelerin bitmesi gerekir.

Başarılar dilerim! 

---

<h2>💡 Proje Hakkında</h2>

Selamlar! Bu projeyi, herhangi bir konu üzerinde çalışırken öğrenme kartlarına veri yüklemenin fazla zahmetli olduğunu düşünerek yapay zekâ desteğiyle tasarladım.

Google Sheets'e veri eklemek, yapay zekâ yardımıyla çok daha kolay hâle geliyor. Ayrıca birden fazla kişi aynı tabloya kelime veya veri ekleyebiliyor. Böylece yeni içerikler oluşturmak ve mevcut verileri güncellemek daha pratik oluyor.

---

<h2>✨ Özellikler</h2>

- **İnteraktif Kartlar:** Kartları çevirerek Arapça kelimelerin Türkçe karşılıklarını görüntüleme.
- **Google Sheets Entegrasyonu:** Kelime verilerini OpenSheet servisi aracılığıyla Google Sheets üzerinden alma.
- **Kelime Seçimi:** Karışık kelimeler ve A1 seviyesi arasında seçim yapabilme.
- **Soru Sayısını Belirleme:** Her kategori için çalışılacak kart sayısını belirleme.
- **Rastgele Sıralama:** Kelime kartlarını rastgele sıralama.
- **Yanlış Cevapları Tekrarlama:** Yanlış cevaplanan kartları tur sonunda yeniden gösterme.
- **İlerlemeyi Kaydetme:** Oyun durumunu tarayıcının `localStorage` özelliğiyle saklama.

---

<h2>🛠️ Kullanılan Teknolojiler</h2>

- HTML5
- CSS3
- JavaScript (ES6+)
- Google Sheets
- OpenSheet servisi
- `localStorage`

---

<h2>🔄 Nasıl Çalışır?</h2>

1. Kelime verileri Google Sheets üzerinde tutulur.
2. Uygulama, OpenSheet servisi üzerinden kelimeleri JSON formatında alır.
3. JavaScript, seçilen kelimeleri işler ve rastgele sıralar.
4. Kullanıcı kartları çevirir ve cevaplarını işaretler.
5. Yanlış cevaplanan kelimeler tekrar gösterilir.
6. Oyun durumu tarayıcının yerel depolama alanında saklanır.


<h2>🔄 Sistem Nasıl Çalışır?</h2>

Bu proje, kelime verilerini Google Sheets üzerinden alan ve bu verileri JavaScript ile interaktif öğrenme kartlarına dönüştüren bir web uygulamasıdır.

<h3>1. 📊 Verilerin Google Sheets Üzerinde Saklanması</h3>

Arapça kelimeler ve Türkçe karşılıkları Google Sheets üzerinde tutulur. Böylece kelimeleri doğrudan HTML kodunun içine yazmak yerine bir tablo üzerinden yönetmek mümkün olur.

Yeni kelimeler tabloya eklenebilir veya mevcut veriler güncellenebilir. Birden fazla kişi de aynı tablo üzerinde çalışarak kelime havuzunun geliştirilmesine katkıda bulunabilir.

Uygulamada farklı kelime grupları ayrı sayfalarda tutulur. Örneğin, `Sayfa1` karışık kelimeler için, `Sayfa2` ise A1 seviyesi için kullanılmaktadır.

Tablodaki sütun başlıkları, uygulamanın beklediği alan adlarıyla eşleşmelidir:

- `Arapça`: Kartın ön yüzünde gösterilecek kelime.
- `Türkçe`: Kartın arka yüzünde gösterilecek karşılık.

<h3>2. 🔗 OpenSheet ile Verilerin Alınması</h3>

Google Sheets verilerini uygulamaya aktarmak için [OpenSheet](https://opensheet.elk.sh/) servisi kullanılmaktadır.

OpenSheet, uygun erişim ayarlarına sahip bir Google Sheets tablosundaki verileri JSON formatında sunar. Böylece uygulamanın Google Sheets API'sini doğrudan kullanması ve ayrıca bir sunucu geliştirmesi gerekmez.

Projede her kelime grubu için bir bağlantı tanımlanmıştır:

```javascript
const URLS = {
  s1: "https://opensheet.elk.sh/...",
  s2: "https://opensheet.elk.sh/..."
};
```

Buradaki adresler, Google Sheets belgesinin kimliğini ve okunacak sayfanın adını içerir. Uygulama, seçilen kategoriye karşılık gelen adresten verileri alır.

<h3>3. 💻 JavaScript ile Verilerin Çekilmesi</h3>

Kullanıcı `Başla` butonuna bastığında `start()` fonksiyonu çalışır. Bu fonksiyon, seçilen kategorileri kontrol eder ve her kategori için istenen kelime sayısını alır.

Veriler aşağıdaki yöntemle çekilir:

```javascript
let r = await fetch(URLS[key]);
let d = await r.json();
```

- `fetch()` belirtilen adrese HTTP isteği göndererek verileri alır.
- `await`, işlem tamamlanana kadar ilgili kodun devam etmesini bekler.
- `r.json()`, gelen yanıtı JavaScript'in işleyebileceği bir veri yapısına dönüştürür.

Bu sayede Google Sheets'teki kelimeler, uygulama tarafından kullanılabilecek bir dizi hâline gelir.

<h3>4. 🃏 Verilerin Kartlara Dönüştürülmesi</h3>

Alınan veriler, aşağıdaki kodla kartların ön ve arka yüzlerine karşılık gelecek şekilde düzenlenir:

```javascript
let list = d.map(x => ({
  front: x["Arapça"],
  back: x["Türkçe"]
}));
```

Burada `map()` fonksiyonu her satırdaki Arapça ve Türkçe alanlarını alır. Böylece her kelime çifti, kartın ön ve arka yüzünü temsil eden bir nesneye dönüştürülür.

Ardından `shuffle()` fonksiyonuyla kelimeler karıştırılır ve `slice()` ile istenen sayıda kart seçilir.

Seçilen kartlar birleştirilir ve son kez karıştırılır. Böylece farklı kategorilerden gelen kelimeler aynı turda sorulabilir.

<h3>5. ✅ Cevapların Değerlendirilmesi ve Tekrar Sistemi</h3>

Kullanıcı, kartı çevirdikten sonra kelimeyi bilip bilmediğini işaretler.

- **Bildim:** Sonraki karta geçilir.
- **Bilemedim:** İlgili kelime, yanlış cevaplanan kelimeler listesine eklenir.
- **Tur sonunda:** Yanlış cevaplanan kelimeler yeniden karıştırılarak tekrar gösterilir.

Aynı kelimenin yanlış cevaplar listesine birden fazla kez eklenmesi engellenir. Böylece tekrar turunda aynı kelimenin gereksiz yere çoğaltılması önlenir.

<h3>6. 💾 Oyun İlerlemesinin Kaydedilmesi</h3>

Uygulama, mevcut oyun durumunu tarayıcının `localStorage` özelliğiyle saklar.

Bu amaçla şu bilgiler kaydedilir:

- Mevcut kart listesi
- Yanlış cevaplanan kelimeler
- Oyunda bulunulan kartın sırası

`JSON.stringify()` verileri metin formatına dönüştürerek saklar. Oyun yeniden açıldığında `JSON.parse()` ile veriler geri alınır ve oyun kaldığı durumdan gösterilebilir.

Bu kayıtlar Google Sheets'e değil, kullanıcının tarayıcısına kaydedilir. Dolayısıyla farklı bir tarayıcıya veya cihaza geçildiğinde aynı ilerlemenin otomatik olarak aktarılması beklenmemelidir.

<h3>7. 🌐 Genel Veri Akışı</h3>

Sistemin çalışma sırası şu şekildedir:

1. Kelimeler Google Sheets üzerinde tutulur.
2. OpenSheet, tablo verilerini JSON formatında sunar.
3. JavaScript, `fetch()` ile verileri alır ve işler.
4. Seçilen kelimeler kartlara dönüştürülür.
5. Kullanıcı cevaplarını işaretler ve yanlış kelimeler tekrar sorulur.
6. Oyun durumu `localStorage` üzerinden saklanır.

Bu yapı sayesinde ayrı bir backend veya veri tabanı sunucusu kurmadan, Google Sheets'i veri kaynağı olarak kullanan basit bir web uygulaması geliştirilebilir.

<h3>⚠️ Erişim ve Veri Güvenliği</h3>

Google Sheets verilerinin OpenSheet üzerinden okunabilmesi için tablonun uygun erişim ayarlarına sahip olması gerekir. Bu nedenle herkese açık erişime izin verilen tablolara gizli veya kişisel bilgiler eklenmemelidir.

OpenSheet, uygulama ile Google Sheets arasında kullanılan harici bir servistir. Bu yüzden uygulamanın çalışması, ilgili servisin erişilebilir olmasına ve tablonun doğru yapılandırılmasına bağlıdır.


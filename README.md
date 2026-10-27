
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



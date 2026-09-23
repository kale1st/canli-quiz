# Canlı Quiz v3 · Kurulum

Bu kurulumu **sadece siz, bir kez** yaparsınız. Öğretmenler hiçbir şey kurmaz. Onlara sadece sitenin adresini gönderirsiniz.

## 1. Firebase projesi (yaklaşık 10 dakika)

1. https://console.firebase.google.com adresine gidin → **Proje ekle** → bir ad verin (ör. `canli-quiz`). Google Analytics'i kapatabilirsiniz.
2. **Authentication** → **Başlayın** → **Oturum açma yöntemi** → **Anonim** → Etkinleştir → Kaydet.
3. **Firestore Database** → **Veritabanı oluştur** → konum olarak `eur3 (europe-west)` seçin → **Üretim modunda başlat**.
4. Firestore'da **Kurallar** sekmesine geçin. İçindekileri silin, `firestore.rules` dosyasının içeriğini yapıştırın ve **Yayınla**'ya basın.
5. Sol üstteki dişli → **Proje ayarları** → aşağıda **Uygulamalarınız** → web simgesi `</>` → bir ad verin → **Uygulamayı kaydet**.
6. Ekranda çıkan `firebaseConfig = { ... }` bloğunu kopyalayın. `ayarlar.js` dosyasındaki `window.FIREBASE_AYAR = null;` satırında `null` yerine bu bloğu yapıştırın.

Fatura bilgisi girmeyin. Ücretsiz planda (Spark) kaldığınız sürece para çekilmesi mümkün değildir.

## 2. GitHub Pages (yaklaşık 5 dakika)

1. https://github.com adresinde **New repository** → ad: `canli-quiz` → **Public** → Create.
2. **Add file → Upload files** → `index.html` ve `ayarlar.js` dosyalarını yükleyin → **Commit**.
3. **Settings → Pages** → Branch: `main`, klasör: `/ (root)` → **Save**.
4. 1–2 dakika sonra site şu adreste açılır: `https://KULLANICI-ADINIZ.github.io/canli-quiz/`
5. Firebase'e dönün: **Authentication → Ayarlar → Yetkili alan adları** → `KULLANICI-ADINIZ.github.io` ekleyin.

Bu adresi öğretmenlere gönderin. Güncelleme yapmak için GitHub'da `index.html` dosyasını yenisiyle değiştirmeniz yeterli.

## Nasıl çalışır

- **Quizler** öğretmenin tarayıcısında saklanır, internete gönderilmez.
- **Yarışma sırasında** veritabanına sadece o anki soru, katılımcıların adı, puanı ve cevapları gider. Doğru cevap, süre bitene kadar gönderilmez.
- **Bitir ve verileri sil** dendiğinde oda tamamen silinir. Unutulan odalar 24 saat sonra, bir sonraki yarışma açılırken otomatik silinir.
- Yarışmayı sadece onu başlatan tarayıcı yönetebilir. Öğrenciler linki alsa da yönetemez.

## Ücretsiz plan sınırları

- Günde yaklaşık **40 yarışma** (20 öğrenci × 20 soru hesabıyla). Aynı anda kaç sınıfın oynadığının önemi yok.
- Kota her gün Türkiye saatiyle **10:00–11:00** arasında sıfırlanır.
- Kota dolarsa uygulama "Bugünkü ücretsiz kullanım kotası doldu" uyarısı verir.
- Kullanımı görmek için: Firebase → Firestore → **Kullanım** sekmesi.

## Önizleme modu

`ayarlar.js` boşsa uygulama önizleme modunda açılır. Veriler sadece o tarayıcıda tutulur. Sağ alttaki **+ Öğrenci sekmesi** düğmesiyle aynı bilgisayarda öğrenci ekranını deneyebilirsiniz.

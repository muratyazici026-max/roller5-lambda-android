# Roller-5 Lambda – Android uygulaması

Roller-5 PL7-APG brülörleri için lambda hesaplayıcı. İnternetsiz çalışır, ölçümler telefonda saklanır.
1. ölçüm (ana fan) ve 2. ölçüm (yedek fan) turları uygulamanın içinde hazır gelir.

## APK'yı almak – Yol A: GitHub (bilgisayara bir şey kurmadan, ~5 dk)

1. github.com'da ücretsiz hesap açın, sağ üstten **New repository** → ad: `roller5-lambda` → **Private** → Create.
2. Açılan sayfada **uploading an existing file** bağlantısına tıklayın.
3. Bu zip'i bilgisayarda açın, **içindeki tüm dosya ve klasörleri** (`.github` klasörü dahil) sürükleyip bırakın → **Commit changes**.
   - Not: `.github` gizli klasör olabilir. Windows'ta Gezgin → Görünüm → "Gizli öğeler"i açın.
4. Üstteki **Actions** sekmesine gidin. "APK derle" işi kendiliğinden başlar (başlamazsa: APK derle → **Run workflow**).
5. Yeşil tik çıkınca (3–5 dk) işe tıklayın, en altta **Artifacts → Roller5-Lambda-APK** dosyasını indirin.
6. İnen zip'in içinden `app-debug.apk` çıkar. Telefona gönderin (WhatsApp/e-posta/USB).

## APK'yı almak – Yol B: Android Studio

1. Android Studio'yu kurun, **Open** ile bu klasörü açın (Gradle eşitlemesi biter).
2. Menü: **Build → Build App Bundle(s) / APK(s) → Build APK(s)**.
3. APK: `app/build/outputs/apk/debug/app-debug.apk`

## Telefona kurulum

APK dosyasına dokunun → "Bilinmeyen kaynaklardan yüklemeye izin ver" uyarısında izin verin → **Yükle**.
Play Protect uyarı verirse "Yine de yükle" deyin (uygulama Play Store'da olmadığı için normal).

## Kullanım notları

- **Yeni tur başlat** → bir brülöre dokun → hava/gaz gir → **Kaydet ve sonrakine geç**.
- **Turu CSV paylaş**: turu Excel'de açılabilir metin olarak WhatsApp/e-postaya gönderir (ayırıcı `;`).
- **Tüm yedeği paylaş**: bütün turları JSON metni olarak gönderir. Yeni telefonda **Yedeği geri yükle** → metni yapıştır.
- Uygulamayı kaldırmak verileri siler; önce yedek alın.

## Güncelleme

Formül veya ekran değişecekse yalnızca `app/src/main/assets/www/index.html` değişir.
Yeni sürümde `app/build.gradle` içindeki `versionCode` değerini 1 artırın; üzerine kurunca veriler korunur.

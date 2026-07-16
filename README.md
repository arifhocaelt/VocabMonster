# YDT Vocab Monster PC Web GitHub Pages Paketi

Bu klasör GitHub Pages'e doğrudan yüklenebilecek statik site paketidir.

## İçerik

- `index.html`: Uygulama ana sayfası ve Play Store bağlantı merkezi
- `app/index.html`: Mevcut YDT Vocab Monster web uygulaması
- `privacy-policy.html`: Google Play gizlilik politikası URL'si
- `account-deletion.html`: Google Play hesap/veri silme URL'si
- `support.html`: Destek URL'si
- `user-guide.html`: Kullanım kılavuzu
- `data-safety.html`: Play Console Data Safety beyanı için çalışma özeti
- `play-store-checklist.html`: Yayın öncesi kontrol listesi

## Yayınlama

1. GitHub'da yeni bir repo oluşturun.
2. Bu klasördeki tüm dosyaları reponun köküne yükleyin.
3. Repository Settings > Pages alanında `main` branch ve `/root` kaynağını seçin.
4. Firebase Console > Authentication > Settings > Authorized domains alanına GitHub Pages domainini ekleyin.
5. GitHub Pages yayınlandıktan sonra Play Console'da şu URL'leri kullanın:

- Privacy policy: `https://<kullanici-adi>.github.io/<repo-adi>/privacy-policy.html`
- Support URL: `https://<kullanici-adi>.github.io/<repo-adi>/support.html`
- Account deletion URL: `https://<kullanici-adi>.github.io/<repo-adi>/account-deletion.html`
- Website: `https://<kullanici-adi>.github.io/<repo-adi>/`

## Yayın öncesi son notlar

- Gizlilik politikasındaki iletişim bölümünü gerçek Play Console geliştirici e-postasıyla uyumlu hale getirin.
- Android APK içinde hesap silme akışı olduğundan emin olun.
- AdMob veya başka SDK eklenirse `privacy-policy.html` ve `data-safety.html` dosyalarını gerçek SDK davranışına göre güncelleyin.

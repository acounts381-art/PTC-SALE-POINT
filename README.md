# PTC Dashboard - Android APK (GitHub Actions + SQLite)

## APK banane ke steps
1. GitHub par naya repository banayein (public ya private).
2. Is zip ki **saari files aur folders** (`.github` folder samet) repository me upload karein (branch: `main`).
   - Agar `.github` folder upload nahi hota to GitHub ke "Add file > Create new file" me
     `.github/workflows/build-apk.yml` naam se file banakar uska content paste karein.
3. Repository ke **Actions** tab me "Build APK" workflow khud chalta hai (ya "Run workflow" dabayein).
4. 5-10 minute baad workflow khatam hone par us run ke page ke neeche **Artifacts > PTC-Dashboard-APK** download karein.
5. Download ki hui zip ke andar `app-debug.apk` hoti hai. Isay phone me install karein
   (Settings me "Install unknown apps" allow karna pad sakta hai).

## Database (SQLite)
- App ka saara data phone ke andar SQLite database `ptc_db` me save hota hai.
- Tables: `shops`, `products`, `bills`, `uploads`, `inventory`, `settings`
  (Dr list, categories, payment methods, colors, holiday, Start Day stock `settings` me hain).
- Har badlav 1-2 second me khud save ho jata hai, aur app band/background hone par bhi save hota hai.
- App dobara kholne par data wahin se wapas aata hai. Shop aur product ki pictures bhi save hoti hain.
- "All Data Clear" database ko bhi khali kar deta hai.
- App uninstall karne ya phone ke Settings se "Clear data" karne par data chala jata hai.
- Pehli baar app khulne par sample shops/products dikhte hain (All Data Clear se hata sakte hain).

## Zaroori baatein
- Ye **debug APK** hai (testing/install ke liye theek, Play Store ke liye nahi).
- Excel export phone me "Save / Share" ka menu kholta hai. Excel upload phone ki files se chalti hai.
- App ka design/code `www/index.html` me hai. Isme changes karke push karein to nayi APK ban jati hai.

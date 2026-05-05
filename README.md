# Taksio — Ödeme Planı

## Kurulum (Windows + VSCode)

### 1. Gereksinimler
- Node.js 18+ → https://nodejs.org
- VSCode
- Git → https://git-scm.com

### 2. Proje kurulumu (VSCode terminali)
```bash
cd taksio-app
npm install
```

### 3. www klasörünü hazırla
```bash
mkdir www
# taksio.html → www/index.html olarak kopyala
# privacy.html → www/privacy.html olarak kopyala
```

### 4. iOS platformunu ekle
```bash
npx cap add ios
npx cap sync
```

### 5. GitHub'a push et
```bash
git init
git add .
git commit -m "ilk commit"
git remote add origin https://github.com/KULLANICI_ADIN/taksio.git
git push -u origin main
```

### 6. GitHub Secrets ekle
Repo → Settings → Secrets → Actions:

| Secret | Nereden alınır |
|--------|---------------|
| BUILD_CERTIFICATE_BASE64 | Keychain'den .p12 export → base64 |
| P12_PASSWORD | .p12 şifresi |
| BUILD_PROVISION_PROFILE_BASE64 | developer.apple.com → Profiles → base64 |
| KEYCHAIN_PASSWORD | Rastgele bir şifre yaz |
| TEAM_ID | developer.apple.com → Membership |
| PROVISIONING_PROFILE_NAME | Profil adı (App Store dağıtım) |

### 7. Build al
GitHub Actions sekmesinde "Taksio iOS Build" workflow'u çalıştır.
IPA dosyası Artifacts bölümünde indirilir.

### 8. App Store Connect'e yükle
- Transporter uygulamasını Mac'e kur (ücretsiz)
- IPA'yı Transporter ile yükle
- App Store Connect → TestFlight → Yayın

## Renk Paleti
- Ana mor: #7C6EF5
- Vurgu teal: #29C98A
- Arka plan: #0E0F14

## Bundle ID
app.taksio.ios

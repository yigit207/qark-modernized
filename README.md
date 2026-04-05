# QARK Modernized

[🇹🇷 Türkçe](#türkçe) | [🇬🇧 English](#english)

---

## English

Modernized version of LinkedIn's QARK (Quick Android Review Kit).

### Changes Made
- `android.support.*` → `androidx.*` migration
- Compatible with Gradle 7.6 + AGP 7.2.0
- Android SDK 33 support added
- `AndroidManifest.xml` exported attribute fix
- Layout XML files updated for androidx
- `SYSTEM_ALERT_WINDOW` permission added (required for tapjacking)
- `ActionBarActivity` → `AppCompatActivity` migration

### Supported API Levels
- minSdkVersion: 16 (Android 4.1)
- targetSdkVersion: 33 (Android 13)
- Recommended for Tapjacking: API 23 (Android 6.0)

### Requirements
- Python 3.x
- Java 11
- Android SDK (build-tools 32.0.0, platform 33)

### Installation
```bash
# 1. Create Python virtual environment
python3 -m venv qark_env
source qark_env/bin/activate

# 2. Install qark
pip install qark

# 3. Clone this repo
git clone https://github.com/yigit207/qark-modernized.git

# 4. Copy modernized template
cp -r qark-modernized/* $(python3 -c "import qark; import os; print(os.path.dirname(qark.__file__))")/

# 5. Install Android SDK components
sdkmanager "build-tools;32.0.0" "platforms;android-33"
```

### Usage
```bash
# APK analysis + exploit APK generation
qark --apk target.apk \
     --exploit-apk \
     --sdk-path ~/Android/Sdk \
     --report-type html

# Install exploit APK to emulator
adb install /home/kali/build/<apk_name>/app/build/outputs/apk/debug/app-debug.apk

# Grant draw over other apps permission
adb shell appops set com.secbro.qark SYSTEM_ALERT_WINDOW allow
```

---

## Türkçe

LinkedIn'in QARK (Quick Android Review Kit) aracının modernize edilmiş versiyonu.

### Yapılan Değişiklikler
- `android.support.*` → `androidx.*` migration
- Gradle 7.6 + AGP 7.2.0 uyumlu hale getirildi
- Android SDK 33 desteği eklendi
- `AndroidManifest.xml` exported attribute fix
- Layout XML dosyaları androidx ile uyumlu hale getirildi
- `SYSTEM_ALERT_WINDOW` izni eklendi (tapjacking için gerekli)
- `ActionBarActivity` → `AppCompatActivity` migration

### Desteklenen API Seviyeleri
- minSdkVersion: 16 (Android 4.1)
- targetSdkVersion: 33 (Android 13)
- Tapjacking için önerilen: API 23 (Android 6.0)

### Gereksinimler
- Python 3.x
- Java 11
- Android SDK (build-tools 32.0.0, platform 33)

### Kurulum
```bash
# 1. Python sanal ortam oluştur
python3 -m venv qark_env
source qark_env/bin/activate

# 2. Qark'ı kur
pip install qark

# 3. Bu repoyu klonla
git clone https://github.com/yigit207/qark-modernized.git

# 4. Modernize edilmiş şablonu kopyala
cp -r qark-modernized/* $(python3 -c "import qark; import os; print(os.path.dirname(qark.__file__))")/

# 5. Android SDK kur
sdkmanager "build-tools;32.0.0" "platforms;android-33"
```

### Kullanım
```bash
# APK analizi + exploit APK üretimi
qark --apk uygulama.apk \
     --exploit-apk \
     --sdk-path ~/Android/Sdk \
     --report-type html

# Exploit APK'yı emülatöre yükle
adb install /home/kali/build/<apk_adi>/app/build/outputs/apk/debug/app-debug.apk

# Draw over other apps iznini ver
adb shell appops set com.secbro.qark SYSTEM_ALERT_WINDOW allow
```

## License
Apache 2.0 - Original: [LinkedIn QARK](https://github.com/linkedin/qark)

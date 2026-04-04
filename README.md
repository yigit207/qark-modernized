# QARK Modernized

LinkedIn'in QARK (Quick Android Review Kit) aracının modernize edilmiş versiyonu.

## Yapılan Değişiklikler
- `android.support.*` → `androidx.*` migration
- Gradle 7.6 + AGP 7.2.0 uyumlu hale getirildi
- Android SDK 33 desteği eklendi
- `AndroidManifest.xml` exported attribute fix
- Layout XML dosyaları androidx ile uyumlu hale getirildi

## Kurulum
```bash
# 1. Python sanal ortam oluştur
python3 -m venv qark_env
source qark_env/bin/activate

# 2. Bağımlılıkları kur
pip install androguard==3.3.5 javalang==0.13.0 jinja2 click six requests

# 3. Bu repoyu klon'la
git clone https://github.com/yigit207/qark-modernized.git

# 4. Qark'ı kur
pip install qark

# 5. Modernize edilmiş exploit_apk şablonunu kopyala
cp -r qark-modernized/* $(python3 -c "import qark; import os; print(os.path.dirname(qark.__file__))")/

# 6. Kullanım
qark --apk uygulama.apk --exploit-apk --sdk-path ~/Android/Sdk --report-type html

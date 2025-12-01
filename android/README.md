# Android Quick Note

```bash

# Generate signin key for APK

keytool -genkey -v  -keystore [key].jks  -keyalg RSA -keysize 2048 -validity 10000  -alias [alias_name]


# Get or see the ssh256 or md5 key for signed key
# Replaced the data in [] with the data you provided during the key generation

keytool -list -v   -keystore [key_path].jks   -alias [alias_name]  -storepass [password]   -keypass [password]

```
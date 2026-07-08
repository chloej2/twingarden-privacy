# .well-known/assetlinks.json — TwinGarden Android App Links

Serves Digital Asset Links verification for `com.gardentwin.app` invite links
(`https://chloej2.github.io/twingarden-privacy/i/?t=<token>`, BL-1079 / BL-1015,
PL-098 §B4).

Currently lists **only the DEBUG keystore SHA-256 fingerprint**
(`6C:C7:DF:A5:1C:46:00:8A:9C:14:A7:CE:F5:38:C5:BA:94:CE:FB:AC:49:50:77:7C:0D:B1:0D:E5:C9:1D:E7:B7`).

## TODO (owner action before Play Store rollout)

Add the **RELEASE** signing SHA-256 fingerprint to the `sha256_cert_fingerprints`
array before the invite-link feature ships to production users installing from
Play Store. Google re-signs the APK with **Play App Signing**, so the fingerprint
to add is the one shown in:

Play Console → *your app* → Setup → App integrity → App signing →
**App signing key certificate → SHA-256 certificate fingerprint**

(NOT your local upload-key fingerprint — that's a different cert once Play App
Signing is enabled.) Add it as an additional array entry alongside the debug one;
both can coexist so debug builds keep working too.

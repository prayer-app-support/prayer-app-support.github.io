# Prayer NFC Universal Links

This repository is the root GitHub Pages site for Prayer’s Universal Link
domain:

`https://prayer-app-support.github.io`

The live association file must remain at this exact path:

`https://prayer-app-support.github.io/.well-known/apple-app-site-association`

## Association

The live association authorizes Prayer's signed iOS application for version 1
NFC card links:

```json
{
  "applinks": {
    "details": [
      {
        "appIDs": ["S46L7RX9F3.com.lighthouse.prayer"],
        "components": [
          { "/": "/nfc/v1/secret-place" }
        ]
      }
    ]
  }
}
```

The app’s Expo config declares `applinks:prayer-app-support.github.io`.
Build a new iOS app after changing this association. Apple’s CDN can take up to
24 hours to fetch a newly changed association file; a fresh install is the most
reliable first verification.

Every NFC card uses this URL; personalization belongs in its second NDEF
record:

`https://prayer-app-support.github.io/nfc/v1/secret-place`

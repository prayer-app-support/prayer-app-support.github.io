# Prayer NFC Universal Links

This repository is the root GitHub Pages site for Prayer’s Universal Link
domain:

`https://prayer-app-support.github.io`

The live association file must remain at this exact path:

`https://prayer-app-support.github.io/.well-known/apple-app-site-association`

## Activate the association

The initial file deliberately has no linked apps. Before releasing an NFC-aware
Prayer build, replace its `details` array with the Apple Developer Team ID:

```json
{
  "applinks": {
    "details": [
      {
        "appIDs": ["YOUR_10_CHARACTER_TEAM_ID.com.lighthouse.prayer"],
        "components": [
          { "/": "/nfc/v1/*" }
        ]
      }
    ]
  }
}
```

The app’s Expo config already declares
`applinks:prayer-app-support.github.io`. Build a new iOS app after activating
the association. Apple’s CDN can take up to 24 hours to fetch a newly changed
association file; a fresh install is the most reliable first verification.

NFC cards use URLs such as:

`https://prayer-app-support.github.io/nfc/v1/grace-home-01`

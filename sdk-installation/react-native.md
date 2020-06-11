---
description: React Native SDK
---

# React Native

### Installation

```bash
npm install --save cobrowse-sdk-react-native
react-native link
```

**Note:** For iOS you need to be using Pods to manage dependencies for `react-native link` to work out of the box \(and also remember to run `pod install` after the link step\).

#### Add your License Key

Please register an account and generate your free License Key at [https://cobrowse.io/dashboard/settings](https://cobrowse.io/dashboard/settings).

This will associate sessions from your mobile app with your Cobrowse account.

```javascript
import CobrowseIO from 'cobrowse-sdk-react-native';

CobrowseIO.license = "<your license key here>";
CobrowseIO.start();
```

#### Add device metadata

To help you identify, search, and filter devices in your Cobrowse dashboard, it's helpful to specify any meaningful metadata. We recommend specifying the end-user's email if available.

You may add any custom key/value pairs you'd like, and they will all be searchable and filterable in your online dashboard. We've added a few placeholders for convenience only - all fields are optional.

```javascript
CobrowseIO.customData = {
    user_email: "react-native@example.com"
};
```

### Try it out

Once you have your app running in the iOS Simulator or on a physical device, navigate to [https://cobrowse.io/dashboard](https://cobrowse.io/dashboard) to see your device listed. You can click the "Connect" button to initiate a Cobrowse session!

### Questions?

Any questions at all? Please email us directly at [hello@cobrowse.io](mailto:hello@cobrowse.io).

### Requirements

* iOS 9.0, Android API 19 or above.


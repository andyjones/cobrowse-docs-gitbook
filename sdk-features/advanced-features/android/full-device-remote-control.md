# Full device remote control

### Overview

Full device remote control for Android, including unattended access, is officially supported starting in our v2.0 release. It uses an accessibility service that must be enabled on the device to grant access.

This feature is supported in API 21 \(5.0 Lollipop\) and above.

### Implementation

Add the following line to one of your resources xml files, eg. in res/values/bools.xml:

```markup
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <bool name="cobrowse_enable_full_device_control">true</bool>
</resources>
```

_Note: Please add this value to a Values resource file, and not an XML resource file._

Enable the accessibility service the Cobrowse SDK will have added in the main device settings, eg. Settings -&gt; Accessibility -&gt; Your App Name. Note: this only has to be done the very first time.

We also have built some logic to detect if accessibility service is running, and if not, to deep link the user to the settings to enable it.

Show the sample UI with:

```java
CobrowseAccessibilityService.showSetup(...);
```

Check if accessibility service is already running with:

```java
CobrowseAccessibilityService.isRunning(...);
```

Deep link user to accessibility settings with:

```java
Intent intent = new Intent(android.provider.Settings.ACTION_ACCESSIBILITY_SETTINGS);
intent.addFlags(Intent.FLAG_ACTIVITY_NEW_TASK);
startActivity(intent);
```

### Notes for unattended access

For unattended full device access, we strongly recommend:

* Please initiate sessions with push notifications, rather than our default sockets. This will enable unattended access, even when your app has been backgrounded a long time, or force closed. More info at [Initiate sessions with push](../../initiate-sessions-with-push.md).
* Please turn off "Require User Consent" prompts at [https://cobrowse.io/dashboard/settings](https://cobrowse.io/dashboard/settings). Otherwise, a user must always accept the consent prompt on the device before a session can start.


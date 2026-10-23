# Privacy Policy — FreshRead

**App:** FreshRead (`com.mkm7dev.freshread`)
**Last updated:** 23 October 2026

FreshRead is an unofficial, open-source Android client for **self-hosted FreshRSS** servers. This
policy explains what the app does and does not do with your information.

> **In short:** FreshRead talks only to the FreshRSS server **you** configure — and, when you ask it
> to, to the website of an article you open. The developer runs no servers and receives nothing.
> There are no ads, no analytics, no trackers, and no accounts with us.

## 1. Information we collect

**None.** FreshRead has no sign-up, no developer account and no advertising, analytics or
crash-reporting services. We operate no servers and receive no data from the app. The app's own
network traffic goes to the server URL you enter.

## 2. Data stored on your device

Everything FreshRead knows stays in the app's private storage on your device:

- **Credentials** — the FreshRSS server URL, your username, your API password, and optional HTTP
  Basic Auth credentials. These are kept in the hardware-backed **Android KeyStore** via
  `flutter_secure_storage` (AES-GCM with RSA-OAEP key wrapping), never in plain-text files or logs.
- **Feeds and articles** — your subscriptions, folders, cached article text and images, and the
  read/starred state of each item, in a private SQLite database.
- **Settings** — theme, reader typography, sync preferences, and similar flags in
  `SharedPreferences`.
- **Sync queue** — read/star changes made offline that are waiting to be sent to your server.

This data is used only to run the app for you. It is never sent to us or to any third party, and it
is removed when you uninstall the app or clear its data in Android Settings.

## 3. Android backup

FreshRead explicitly **opts out** of Android cloud backup and device-to-device transfer
(`android:allowBackup="false"` with matching data-extraction rules). Your cached articles,
preferences and credentials are therefore not copied to Google Drive or to another device by the
operating system.

## 4. Permissions we request

FreshRead asks only for what a feed reader needs:

- **Internet and network state** — to reach the FreshRSS server you configure.
- **Run at startup, wake lock, foreground service** — to run the optional periodic background sync
  (Android's WorkManager library).
- **Notifications** — declared by the WorkManager library. FreshRead does **not** send push
  notifications or any notifications about articles.
- **Google Play billing** — only for the optional donations described in §6.

The app does not request location, contacts, camera, microphone, SMS, call logs, storage or
accessibility permissions.

## 5. Network communication

1. **Your FreshRSS server.** All syncing — login, subscriptions, articles, read/star changes — is
   sent to the server URL you enter. Your credentials are sent there and nowhere else.
2. **Article websites.** When you tap an article, or when "Fetch full article" is enabled, FreshRead
   requests that page directly from the publisher's website so it can extract the readable text.
   That request is made without your FreshRSS credentials and without any account data; the
   publisher sees it as an ordinary page visit from your IP address, exactly as if you opened the
   page in a browser.
3. **Images** in articles are loaded from the publisher's servers or its image CDN and cached on your
   device for offline reading.
4. **Opening links** hands the URL to your browser or an Android Custom Tab. What that browser does
   is governed by its own privacy policy.

FreshRead has no developer-operated backend, proxy or relay. If you configure a plain **HTTP**
server, that traffic is unencrypted; the app warns you before connecting that way.

## 6. In-app purchases (optional donations)

FreshRead offers **optional, voluntary donations** under **Settings → Support**, using **Google Play
Billing**. Purchases are processed entirely by Google Play. We do **not** receive your name, card
details or any payment information. Google may report an anonymous purchase confirmation to the app
so it can thank you and let you donate again. Donating unlocks **nothing** — every feature is
available for free. Google's handling of purchase data is governed by
[Google's Privacy Policy](https://policies.google.com/privacy).

## 7. Third-party components

The app is built with Flutter and uses these components:

- **Google Play Billing** — optional donations (§6).
- **AndroidX WorkManager** — optional periodic background sync.
- **Drift / SQLite** — local database.
- **cached_network_image** — local image cache.

There is no analytics SDK, no advertising SDK, no crash reporter and no social login. These
components do not send data to the developer.

## 8. Data sharing

We do not sell, rent or share your information, because we never receive any. The only parties your
device talks to are the FreshRSS server you configured and, when you request it, the websites that
published the articles you read.

## 9. Data retention and deletion

- **Cache** — cached articles are kept for about 30 days by default. Starred articles and changes
  still waiting to sync are never deleted automatically.
- **Clear cache** — **Settings → Storage → Clear cache** deletes cached articles on the device.
- **Sign out** — removes the stored server credentials and tokens from the KeyStore and clears the
  local feed database.
- **Uninstall** — removes everything FreshRead stored on the device.

## 10. Children's privacy

FreshRead is a general-purpose news reader and is not directed to children under 13. We do not
knowingly collect information from children — we collect no information from anyone.

## 11. Security

Credentials are held in the Android KeyStore. Article data lives in the app's private, sandboxed
storage. Prefer **HTTPS** for your FreshRSS server: over plain HTTP, your username, API password and
articles travel unencrypted across the network, and FreshRead warns you before you connect that way.

## 12. Content and disclaimer

Articles, images and links are supplied by the feeds **you** subscribe to and by the publishers
behind them. We do not control, moderate or endorse that content. FreshRead is provided **"as is"
and "as available"**, without warranties of any kind. The developer is not liable for any loss or
inconvenience resulting from content shown in the app, from a failed sync, or from a page that could
not be fetched. FreshRead is not affiliated with the FreshRSS project.

## 13. Changes to this policy

We may update this policy from time to time; the "Last updated" date above will change. Continued
use of the app after an update means you accept the revised policy.

## 14. Contact

Questions about this privacy policy? Contact: **mohammedalmuallem1@gmail.com**

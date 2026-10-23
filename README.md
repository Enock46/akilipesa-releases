# AkiliPesa – Android downloads

This repository only hosts the Android app (APK) for **AkiliPesa**, the personal budgeting app for Tanzania. It contains no source code.

- **Download the latest version:** https://github.com/Enock46/akilipesa-releases/releases/latest/download/AkiliPesa.apk
- **Website:** https://akilipesa.co.tz
- **Web app (any phone or computer):** https://app.akilipesa.co.tz

## Installing

1. Download `AkiliPesa.apk` on your Android phone.
2. Open it. If asked, allow installing apps from this source.
3. Tap **Install**.

Updating: download the newest APK and install it over the old one. Your budget stays on your phone.

## Sending a message to everyone (announcements)

Edit `announcements.json` in this repo (the pencil icon on GitHub) and commit. The app shows the first active announcement at the top of the home screen within a few hours, on Android and on the web. People can close it; it then stays closed for them.

```json
{
  "announcements": [
    {
      "id": "new-feature-loans",
      "title": { "en": "Track money you lend", "sw": "Fuatilia pesa unazokopesha" },
      "message": { "en": "Open Goals & Loans to record who owes you.", "sw": "Fungua Malengo & Mikopo kurekodi anayekudai." },
      "link": "https://akilipesa.co.tz",
      "linkLabel": { "en": "Learn more", "sw": "Jifunze zaidi" },
      "until": "2026-12-31"
    }
  ]
}
```

- `id` must be new for each message (reusing one means people who closed it will not see it).
- `link`, `linkLabel` and `until` are optional. `until` is the last day it shows.
- Optional `"platforms": ["android"]` or `["web"]`, and `"minVersion"` / `"maxVersion"` (for example `"1.0.3"`) target who sees it.
- To stop showing it, remove it from the list (or let `until` pass).

## Updating the "Buy a coffee" link (every week)

The Snippe payment link expires after 7 days. When you make a new one, edit `support.json` here (pencil icon on GitHub), paste the new link into `url`, update `updated`, and commit:

```json
{
  "url": "https://snippe.me/p/NEW-LINK",
  "updated": "2026-10-30"
}
```

The app (Settings → About → Support AkiliPesa) and the website footer pick it up within a few hours. No app update needed. Remove the `url` (or the file) to hide the button.

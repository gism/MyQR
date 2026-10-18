# MyQR

A self-contained web tool that reproduces an encrypted rolling QR code.

**Live site: https://gism.github.io/MyQR/**

## What it does

- Builds the app's field string (`UID`, local time, synced time, UTC offset, optional GPS).
- Encrypts it exactly as the app does and renders the result as a QR code at error-correction level M.
- Lets you edit every field, including the Android ID (defaults to a random value; press **Randomize** for a new one).
- Remembers the last Android ID per browser, so your value is restored on the next visit.
- **Use my phone's location** fills in GPS coordinates (needs an https page and location permission).
- Includes a decoder to recover the plaintext from any scanned QR.

## Usage

Open the live site, set the fields you need, and scan or save the generated QR. On a phone, GPS works because the page is served over https.

## How to get your Android ID

**Exact match (recommended).** This is the ID the original app actually uses:

1. Open the original app and let it display its QR.
2. Scan that QR with any scanner (or screenshot it) to get the hex string.
3. Paste the hex into the **Decoder** on the page.
4. The decoded `UID=STAD…` contains your Android ID — copy the part after `STAD` into the Android ID box.

**Quick option.** Install a free Device ID app and copy its "Android ID":

- Device ID (Evozi): https://play.google.com/store/apps/details?id=com.evozi.deviceid

Since Android 8, `ANDROID_ID` is scoped per app, so a Device ID app may report a value that does **not** match the original app's QR. Use the exact-match steps above when the generated code must be accepted by the same system.

## Notes

- All logic runs in the browser; nothing is sent to a server. The remembered Android ID stays in your own browser's storage.
- This is a testing/demonstration tool for the encrypted QR format.

# MyQR

A self-contained web tool that reproduces the SmartTagQR app's encrypted rolling QR code.

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

## Notes

- All logic runs in the browser; nothing is sent to a server. The remembered Android ID stays in your own browser's storage.
- This is a testing/demonstration tool for QR codes produced by the SmartTagQR app.

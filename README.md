# PDF Print Utility v3 — manual page entry fixed

## Fixed
- `32` is now accepted correctly.
- `1-20` is accepted.
- `1,3,5,10-12` is accepted.
- Odd/even selections work.
- Reverse keeps reverse print order.
- 45 MB PDFs are kept as binary data, not Base64.
- Print prepares only selected pages.

## Printer behavior
A normal web page cannot discover arbitrary Wi-Fi printers or send a raw print command directly to them. Chrome/Android owns the printer dialog for security.

When Print is pressed, this web app prepares the selected PDF pages and calls the browser's native `window.print()` flow. The Android system print screen is where the user chooses an available/configured Wi-Fi printer.

## If you need exactly this workflow:
`Print → show Wi-Fi printers → select printer → send print job directly`

then the correct implementation is a **native Android app**, not a browser-only web app. A native Android version can integrate with Android's printing framework and provide the printer-selection workflow. The web UI can remain the same.

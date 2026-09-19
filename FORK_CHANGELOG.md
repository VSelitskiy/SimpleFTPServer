# Fork changelog

This file records changes specific to the VSelitskiy fork. Upstream SimpleFTPServer history remains in the main README.

## 3.0.2-vs.1 — 2026-09-19

Base: SimpleFTPServer 3.0.2 by Renzo Mischianti.

ESP32 reliability changes:

- Added safe handoff of an idle FTP control session when FileZilla opens a new control connection.
- Prevented control-session replacement while LIST, STOR or RETR is active.
- Added a short handoff guard after accepting a new control connection to avoid immediate session stealing during authentication.
- Restarted the authentication timeout after a valid USER command while waiting for PASS.
- Updated control-channel parsing so readChar() consumes all currently available bytes until a complete command line is assembled.

Validation scope:

- Three independent devices.
- ESP32-S3 and classic ESP32.
- Wi-Fi networking.
- LittleFS storage.
- FileZilla client.
- Repeated listing, upload, download, disconnect and reconnect operations.

No additional validation is claimed for other MCU families, network interfaces or storage backends.

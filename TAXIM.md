# Taxim Remote Support (택심 원격지원)

This repository is a **modified version of [RustDesk](https://github.com/rustdesk/rustdesk)**,
used by a tax accounting office to help its own clients on their PCs.
It is distributed under the same license as RustDesk, **AGPL-3.0** (see `LICENCE`).
RustDesk is a trademark of its owners; this build is not affiliated with or endorsed by them.

Based on RustDesk tag `1.5.1`. Branch: `taxim`.

## What is changed

- Built-in rendezvous/relay server and public key of our own self-hosted server (`src/common.rs`, `load_taxim_builtin`).
- A session always needs a click on **[Accept]** at the controlled PC (`approve-mode = click`).
- "Customer mode": when the executable file name contains `-qs-`, the program only receives
  connections and shows a minimal window (no settings, no install, no account, no address book).
- Window title / customer window text in Korean (`flutter/lib/common.dart`, `flutter/lib/desktop/pages/desktop_home_page.dart`).
- GitHub Actions reduced to a Windows x64 build (`.github/workflows/taxim-windows.yml`).

## Build

Push to the `taxim` branch (or run the "Taxim Windows build" workflow). The executable is
attached to the `taxim-latest` pre-release.

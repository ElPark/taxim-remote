# Taxim Remote Support (택심 원격지원)

A small remote-support client for Windows, used by a Korean tax accounting office to help
its own clients on their PCs (for example, while filing taxes together on the phone).

This is a **modified version of [RustDesk](https://github.com/rustdesk/rustdesk)** (tag `1.5.1`),
distributed under the same license, **AGPL-3.0** (see [`LICENCE`](LICENCE)).
RustDesk is a trademark of its owners; this project is not affiliated with or endorsed by them.
The original RustDesk README is kept at [`docs/README-RUSTDESK.md`](docs/README-RUSTDESK.md).

- Source branch: [`taxim`](https://github.com/ElPark/taxim-remote/tree/taxim)
- Download: [Releases → `taxim-latest`](https://github.com/ElPark/taxim-remote/releases/tag/taxim-latest)
- [Code signing policy](CODE_SIGNING_POLICY.md) · [Privacy](PRIVACY.md) · [What is changed](TAXIM.md)

## What it does

- **The person at the PC is always asked.** A session starts only after the person sitting at the
  controlled PC clicks **[수락] (Accept)**. There is no unattended access and no password-only access.
- **Customer mode.** When the downloaded file name contains `-qs-`, the program only *receives*
  a connection and shows one small window: what to do next, the PC number, and a Quit button.
  Nothing is installed; closing the window ends it.
- **Staff mode.** The same executable under its normal name is the regular client the office staff
  use to connect.
- It talks only to the self-hosted rendezvous/relay server of the office (address and public key are
  built in). It does not use the public RustDesk servers and does not check for updates.

## How to use

Customer: download the file from the support page of the office, run it, tell the staff member the
number on the screen, click **[수락]** when asked. To stop, click Quit or close the window.

Uninstall: customer mode installs nothing. The unpacked program files are in
`%LOCALAPPDATA%\taximremote` and its settings in `%APPDATA%\TaximRemote`; delete both folders to
remove every trace.

## Build

Builds run only on GitHub Actions ([`taxim-windows.yml`](.github/workflows/taxim-windows.yml)) from
the `taxim` branch, and the result is attached to the `taxim-latest` pre-release.
[`taxim-smoke.yml`](https://github.com/ElPark/taxim-remote/blob/taxim-smoke/.github/workflows/taxim-smoke.yml)
runs the published build on a clean runner and publishes screenshots.

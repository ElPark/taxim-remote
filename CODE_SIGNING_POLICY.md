# Code signing policy

> Status: **applied for, not yet granted.** Current releases are unsigned.
> Once granted: free code signing provided by [SignPath.io](https://signpath.io), certificate by
> [SignPath Foundation](https://signpath.org).

## What is signed

Only the Windows executable `taxim-remote-<version>-x86_64.exe` that the GitHub Actions workflow
[`taxim-windows.yml`](.github/workflows/taxim-windows.yml) builds from the `taxim` branch of this
repository. No binary built anywhere else is signed. Every signing request is approved manually.

This project is a fork of [RustDesk](https://github.com/rustdesk/rustdesk), which publishes signed
builds; the `taxim` branch is based on the upstream release tag `1.5.1`. The package also contains
unmodified open-source components built by the upstream workflow (see [`TAXIM.md`](TAXIM.md)).

## Team roles and their members

| Role | Member |
| --- | --- |
| Committers and reviewers | [ElPark](https://github.com/ElPark) |
| Approvers | [ElPark](https://github.com/ElPark) |

Changes proposed by anyone else (pull requests) are reviewed by a team member before merging.
All team members use multi-factor authentication for the source repository and for SignPath.

## Privacy policy

See [`PRIVACY.md`](PRIVACY.md). In short: this program will not transfer any information to other
networked systems except to the support servers of the office named there, which is what the user
asks for by starting a support session.

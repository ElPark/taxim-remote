# Privacy

Taxim Remote Support is run by a person who wants the office staff to see and control their PC
for a support session. It contacts only the systems below, all operated by the office.

| System | What is sent | Why | Stored? |
| --- | --- | --- | --- |
| Rendezvous/relay server `211.233.208.90` (self-hosted RustDesk server) | The ID and public key of the program, the network address of the PC, and - during a session - the end-to-end encrypted screen/keyboard/mouse traffic | To let the two programs find each other and connect | ID, public key and last address are kept by the server software; session contents are not stored |
| Office website `taxim.co.kr` (customer mode only, when the file was downloaded from the support page of the office) | Every 15 seconds: the ID and version of the program. Once: basic system information (computer name, user name, OS, CPU, memory) as sent by the upstream RustDesk client | So the screen of the staff member shows "ready" without the customer typing the ID | Only the ID of the program is stored, on the support-session record. The system information is discarded on receipt and not stored |

It does **not** contact the public RustDesk servers, does not check for updates, has no analytics,
and sends nothing to any third party.

- A session starts only after the person at the PC clicks **[수락] (Accept)**, and they can end it
  at any time by closing the window.
- To stop all of the above, close the program. Customer mode installs nothing; delete
  `%LOCALAPPDATA%\taximremote` and `%APPDATA%\TaximRemote` to remove it completely.

Contact: open an issue at <https://github.com/ElPark/taxim-remote/issues>.

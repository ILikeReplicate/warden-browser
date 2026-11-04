# Security

## Reporting a problem

Found a way to get around Warden's protections, a bug that leaks data, or anything wrong with how updates are checked? Please **don't open a public issue**. Use **[Report a vulnerability](../../security/advisories/new)** on this repository's Security tab, so it stays private until it's fixed.

Tell us what you found, how to reproduce it, and which Warden version you're on (Settings → About).

## Supported versions

Only the newest release gets fixes. Installed copies update themselves within a few hours of a release and install it the next time Warden closes, so almost everyone is on the newest one.

Warden **0.8.0 and 0.8.1** download updates but can't install them. If you somehow have one of those, install the latest release by hand once.

## How Warden stays patched

- **Main Warden** runs on the newest stable Electron (Chromium). **Warden Media**, the copy for Netflix and other protected video, runs on castlabs' newest Widevine build of Electron.
- Every week both engines are checked for new releases. When there's one, Warden is rebuilt and smoke-tested (window, Shield, pages, Google sign-in, Widevine), and published only if every check passes.
- Each release's security fixes are listed in [CHANGELOG.md](CHANGELOG.md) and in Warden's own *What's new* page.

## How updates are verified

1. Warden downloads `latest.json` and `latest.json.sig` from this repository's latest release.
2. It checks the Ed25519 signature on `latest.json` against the public key built into Warden. The private key never leaves the developer's PC and is never uploaded.
3. It refuses any version that isn't newer than the installed one (no downgrades).
4. The installer link must point at this repository's own releases.
5. The installer is downloaded without cookies, in a separate session, and must match the SHA-256 and size in the signed `latest.json`. Anything else is deleted.
6. It's installed silently when Warden closes, into the same folder, as you (never as administrator).

## Hardening at a glance

- Electron's security fuses are on in main Warden: it can't be used as a Node.js script runner, can't have code injected through environment variables, and keeps cookies encrypted on disk.
- Web pages run sandboxed with context isolation. Warden's own interface talks to the engine only through an allow-list of messages.
- Downloads are quarantined until Microsoft Defender has scanned them.
- Google, Microsoft, Steam, Epic, Riot and Discord sign-in pages are left untouched, so they see a plain, unmodified Chromium.

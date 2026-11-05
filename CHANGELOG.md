# Warden update log

Every Warden release, newest first: what’s new, what’s fixed, security fixes, and the sources checked before deciding things. The same log opens inside Warden after each update, and is always in **Settings → About → What’s new**.

Installed copies update themselves. To install Warden for the first time, get the latest **Warden-Setup** from [Releases](../../releases/latest).

## 0.9.1 · Updates while Warden is closed

*5 November 2026*

Warden now updates itself even while it’s closed, so it’s already on the newest version when you open it. Plus: PC tune-up never asks for admin rights, setup animates again, and Back gets you out of history traps.

### New

- Updates while Warden is closed, like Chrome: once an hour a Windows scheduled task (for your account only, no admin) runs Warden in the background with no window. If a new version is out and Warden isn’t open, it downloads it, checks its signature and installs it, so the next time you open Warden it’s already up to date. If Warden is open, it does nothing (the open Warden updates itself). Updates switched off in Settings → About means this does nothing too; uninstalling Warden removes the task.
- Back gets you out of history traps: a page that adds a pile of history steps so Back keeps you on it is now skipped in one press (Back button, Alt+←, or the page menu), and Warden says so. Pages that only update their address while you scroll aren’t affected. (Thanks, Grok.)
- Right-click the Back button for the pages behind you, like in Chrome. Steps one page added to itself show as one line (“20 steps”).
- A flood of blocked popups from one site is one notice with a count, not a stack of them. (Thanks, Grok.)

### Fixed

- Ctrl+, (Settings) and other Warden pages always open in their own tab instead of replacing a new tab you were on.
- Adding a game always confirms it, even when the library needs a refresh to show it.
- Setup stood still on PCs where Windows’ “Animation effects” setting is off (common, and always the case over Remote Desktop and in Windows Sandbox): the steps no longer slid in and the artwork didn’t move. Setup now always animates; only Warden’s own Animations switch (Settings → Appearance) turns it off.

### Security

- PC tune-up no longer asks for administrator rights at all. Turning on GPU scheduling used to show a Windows permission prompt that only said “Windows Command Processor”, a prompt malware on the PC could have imitated while you were expecting it. That one setting now opens Windows’ own Graphics settings page instead. (Thanks, Grok.)
- Fake sign-in windows drawn inside a page (Steam, Discord, Google, Microsoft, Roblox, Epic): the detector no longer misses a fake address bar that has an extra character, icon or word in front of the address. (Thanks, Grok.)
- Game focus raises your game to “Above normal” instead of “High”: still ahead of every other app (they’re below normal and in Efficiency mode), without the risk of starving Windows’ own mouse and sound handling. (Thanks, Grok.)
- A new refresh rate is now a trial: Warden asks “Keep this refresh rate?” and switches back by itself after 15 seconds without an answer, even if the screen goes black. It’s only saved once you click Keep. (Thanks, Grok.)

## 0.9.0 · Your game comes first

*5 November 2026*

Tell Warden whether you game, stream or work, and it keeps your game first while it runs, checks Windows for settings that cost you FPS, and fixes them with one click each.

### New

- Gamer, Streamer or Workstation: Warden asks how you use your PC (in setup, or once after this update) and tunes itself for it. Change it any time in Settings → PC tune-up.
- Game focus: while a game runs, your other apps go into hiding (low priority plus Windows’ Efficiency mode) and the game gets top priority. Alt-tab to any app and it gets its full speed back while it’s in front. Voice chat, music, OBS, anti-cheat, mouse and headset software are never touched, and everything is put back when the game closes.
- Streaming: with the Streamer profile, OBS (or Streamlabs, XSplit, Twitch Studio) gets priority over the game, so the stream doesn’t drop frames when the game pushes the PC hard.
- PC tune-up: checks Windows Game Mode, background game recording, optimizations for windowed games, mouse acceleration, the power plan and hardware GPU scheduling, and fixes each with one click. Every fix can be undone.
- It also catches monitors left at 60 Hz that can do more (very common after a new monitor or a driver update) and switches them to their real refresh rate.
- Drivers and hardware: how old your graphics driver and BIOS are, with a button to the maker’s own app or page (never a “driver updater” site); RAM running below its rated speed (XMP/EXPO) or on one stick; a nearly full system drive; too many startup apps.
- Updates now reach you even if Warden never closes properly: a downloaded update installs the next time Warden opens (with a small progress window), and if Warden stays open for days it restarts itself to update once the PC has been idle for 20 minutes, with nothing playing, downloading or gaming, and all your tabs come back.

### Fixed

- If you had an extra copy of Warden (for example an old shortcut to another folder), that copy kept opening on an old version. Warden’s shortcuts now always point at the installed copy.

### Security

- PC tune-up never turns off Windows Security, Memory integrity or the firewall for speed. Its fixes only change the settings listed, save what was there before, and the one fix that needs administrator rights (GPU scheduling) asks Windows for permission first.

## 0.8.9 · Updates that just happen

*5 November 2026*

Closing and reopening Warden now really gets you the newest version, without ever downloading an installer yourself.

### New

- Warden checks for an update a few seconds after it opens (it used to wait 45 seconds), and the button by the address bar shows "Updating · 40%" while it downloads.
- Closing Warden in the middle of an update download no longer loses it: the window closes, Warden quietly finishes the download, installs it and then exits. Opening Warden again meanwhile just brings it back.
- Every update check and its result is written to an update log on your PC (%LOCALAPPDATA%\Warden\Updates\updater.log), so if an update ever doesn’t arrive, the reason is there.

### Fixed

- Turning Warden off and on again didn’t update it: it only started downloading 45 seconds after opening, and installed the next time you closed it, so quick restarts never got there.

## 0.8.8 · No more "Leave site?" traps

*5 November 2026*

Pages you never used can’t hold you with a "Leave site?" question any more, and the Shield receipt is easier to see.

### Fixed

- The Shield receipt (click the shield in the address bar) blended into white pages. It now has a soft shadow and outline that follow its torn edge.

### Security

- A page can only ask "Leave site?" if you actually typed or clicked in it, and only once, like in Chrome. Scam pages that never had your attention used it to keep you on them, and the question paused all of Warden until you answered.

## 0.8.7 · Steam API-key scam warning

*5 November 2026*

A warning for one of the most effective Steam scams, which no blocklist can catch because it happens on Steam’s own website.

### Fixed

- Warning pages (fake sites, scams) now show a warning sign in the tab instead of the blocked site’s own logo. 0.8.6 said this was fixed, but Warden still looked up a logo for the address; now it really is.
- Settings → VPN: the "Use a VPN" and "VPN is off" cards still sat on top of each other.
- Settings → About: in copies that can’t update themselves, the automatic-updates switch now shows off, not a dimmed "on".
- Games tab with no games: the free games now sit right under the message, centred, instead of far below it.
- Setup: the text lines up with the buttons again, and long steps fade out above the buttons instead of running into the line.
- Importing from another browser now shows each browser’s own icon instead of letters like "GC" and "ME".

### Security

- Opening Steam’s "Web API key" page now shows a warning first. Scammers talk people into creating a key (for a "trade bot", a "skin site login" or "to verify your account"), then use it to quietly swap their trade offers and take their items. The page is real Steam, so phishing lists can’t stop it. Developers can carry on with one click.

## 0.8.6 · Fake virus warnings stopped

*5 November 2026*

Warden now catches tech-support scams (fake "your PC is locked, call Microsoft" pages), plus a batch of fixes found while testing Warden overnight in a throwaway copy of Windows.

### New

- Tech-support scam protection: pages pretending to be a Windows or Microsoft security alert, with a number to call, get a red warning. If the page took over the screen, Warden takes it out of full screen and mutes it first. A news article about these scams isn’t flagged.
- Esc always leaves a page’s full screen, even when the page tries to lock the keyboard (scam pages do this so you can’t get out).

### Fixed

- Pressing Ctrl+L (or Ctrl+K, Ctrl+E, Ctrl+T) on a page and typing straight away could lose the first letter, so "http://" became "ttp://". Warden now takes the keyboard the instant you press the shortcut, and anything typed in that moment goes into the address bar.
- With no games installed, the Games tab now still shows this week’s free games.
- Settings → VPN: the Server and Port boxes were drawn about 200 pixels tall, and the Port box ran off the edge.
- The fake-site warning let the page underneath show through its text. Warnings now cover the page completely.
- A blocked site’s tab no longer shows that site’s own icon.
- The "What’s new" tab had no icon.
- Two separate setting cards sat almost on top of each other (Accounts, General, VPN). They now have room between them.
- Checkboxes (Privacy & data → Clear browsing data) were bright white boxes on the dark theme; they now match it.
- The "Import bookmarks" button’s icon was oversized and almost invisible.
- The main menu touched the right edge of the window.
- Setup: the last screen mentioned Bitwarden twice, and on short windows the text ran right up to the buttons.
- Settings → About no longer shows an "on" automatic-updates switch in copies that can’t update themselves.
- History’s empty page now explains what shows up there, with a button to import history from another browser.
- Settings → Shortcuts listed "Close tab" twice.

## 0.8.5 · Fixes from an outside security review

*5 November 2026*

Grok tested 0.8.3 like an attacker would. This release fixes what it found, from a popup flood that could crash Warden to fake Steam logins and disguised addresses, and every fix is now part of the attack test each release has to pass.

### New

- Updates arrive faster: Warden checks every hour instead of every 4 hours, and soon after your PC wakes from sleep.
- A frozen page (one stuck in an endless loop) gets a "isn’t responding" notice with Wait or Restart page, and Reload now really restarts it, like Chrome’s "Page unresponsive".
- The sidecar window has a small close button that’s always in its corner, and Esc closes it.
- Typing another browser’s settings address (chrome://settings, about:config) opens Warden’s own Settings, with a note saying so.

### Fixed

- A page could open a flood of tabs until Warden ran out of memory and crashed, losing your tabs. One click now opens at most one popup, a page that nobody clicked can’t open tabs at all, and every page has a hard limit per minute, even on sites whose popups you allowed. Blocked floods get one notice, not one each.
- Clicking the page to close the downloads panel (or any Warden popup) swallowed that click. It now closes the popup and the click lands on the page, like in Chrome. Esc closes them even while the page has focus.
- "Go back" on a fake-site warning opened an empty new tab instead of staying on the page you came from.
- Importing passwords from a file with nothing usable in it said nothing at all. It now says what happened (how many rows were skipped and why), and refuses files far too big to be a password export.
- Enter now saves in Add login (Settings → Passwords), and Esc closes the form.
- A "don’t ask again" choice (like the default-browser question) could be forgotten if Warden crashed right after. Settings are now written to disk straight away.
- Real international addresses with accented letters (like münchen.de) no longer get a "mixes alphabets" fake-site warning.
- Setup no longer pops Bitwarden’s window up over Warden when you finish (it stole your typing). It offers a one-click "Open Bitwarden" instead.

### Security

- Fake Steam login windows drawn inside a page (browser-in-the-browser) are caught in more forms: when the fake address bar is split into pieces, shown in a read-only box, or the fake window is centred instead of pinned. A normal site that just mentions Steam next to its own login isn’t flagged.
- Look-alike addresses written in punycode with an invisible character hidden inside (like a fake "stamcommu nity.com") now get the fake-site warning, showing where the hidden character is.
- Links that open other apps now use an allowlist: only known ones (Steam, Discord, Epic, Spotify, mail, Zoom, Teams and a few more) can even ask, and Steam links only in their everyday forms (store pages, installing or starting a game). Everything else, including ms-settings:, ms-appinstaller:, steam://connect and unknown link types, is refused without a prompt.
- Websites can no longer open Warden’s internal pages or resources (warden:, warden-res:) or network share paths.
- Permission prompts: "Always allow this site" now starts unticked, so one wrong click on Allow isn’t permanent. Blocking is still remembered, so sites can’t keep asking.
- Downloads named like Windows devices (CON, NUL, COM1…) or ending in a dot are renamed safely.
- All of the above are now in the attack test every release must pass inside Windows Sandbox (now 48 checks).

## 0.8.4 · A games library that looks the part

*5 November 2026*

The Games tab is rebuilt: sections, big wide artwork for the games that matter, real cover art for every store, and a free-games list with a quality standard. Plus animated setup, drag-to-copy in the address bar, and a new security test every release must pass.

### New

- The Games tab is in sections: Continue playing, Jump back in, Favorites, Most played (ranked), Rediscover, Installed but never played, Free games, then your whole library. The sections follow the store you pick, so the Steam or Xbox view gets them too.
- One layout rule everywhere: each row’s highlights (your most recent games, your top game, the most-played) get the wide artwork, and the rest are posters at the same height. In the full library, your favorites and most-played games are wide.
- Wide cards use the artwork each store makes for that shape (Steam’s main capsule, Xbox’s titled art, Epic’s wide image), so titles and characters aren’t cut off.
- Rows scroll sideways with the mouse wheel, with arrows on hover and faded edges where there’s more. No scrollbar to drag.
- Free games: free-to-keep games (and Steam games 95% or more off) from Steam, Epic, GOG, Xbox, PlayStation, Nintendo and Ubisoft, biggest first, 10 in the row and up to 50 under "See all".
- Xbox / Game Pass, Riot, Roblox and Epic games now get real cover art: Xbox games from the Microsoft Store’s own listing for that exact game, others from Steam or the Microsoft Store when the title matches exactly. Each game is looked up once and remembered.
- Setup is animated: steps slide in, their options appear one after another, the artwork gently floats and twinkles, and the last step’s checkmark draws itself. With Windows’ “reduce animations” setting on, it stays still.

### Fixed

- Dragging across the address bar to highlight part of the address selected everything instead, so Ctrl+C copied the whole thing. A click selects the whole address and a drag selects just what you drag over, like in Chrome.
- Your Google profile picture sometimes showed as a letter: when Google was slow to send the picture, Warden gave up. Warden now remembers the last picture for each account, and keeps showing your account if Google can’t be reached for a moment.
- Xbox and Riot games showed a small logo on a dark card instead of their artwork.

### Security

- Free games have a standard: only established games (1,000+ positive Steam reviews, or one of Epic’s own hand-picked weekly games), and only when they’re claimed on the official store’s own page. Giveaway links are followed to see where they really land; third-party key sites, sign-up walls and unknown downloads are left out.
- Every release now has to survive an attack test before it’s published: 35 attacks against a test copy, including fake updates (wrong key, forged signature, tampered or oversized installer, downgrades), pages trying to reach your files or Warden’s internals, ClickFix clipboard tricks and five ways around Warden’s clipboard guard, wallet-address swaps, silent clipboard reads, camera/location/notification grabs, cheat-injector downloads, look-alike Steam sites and plain-http downgrades. Each trick is first run with harmless data to prove it really works, so a pass means Warden stopped it, not that the trick failed by itself.
- Releases are also installed and tested inside Windows Sandbox, a throwaway copy of Windows, before they’re published, and the publishing tool refuses any build that didn’t pass both tests that day.
- Cover-art and free-game lookups send only game names (or Microsoft Store package names) to Steam, Microsoft, Epic, GamerPower and CheapShark, in separate sessions with no cookies.

### What we looked up

- [GamerPower’s public giveaway feed, used to find free-to-keep games across stores.](https://www.gamerpower.com/api-read)
- [CheapShark’s deals API, used for Steam games 95% or more off.](https://apidocs.cheapshark.com/)

## 0.8.3 · See which account you’re in

*4 November 2026*

With more than one account, the account button shows your picture and first name, so you can tell at a glance which Gmail a tab is using.

### New

- The account button shows the account’s first name next to its picture when you have more than one account, like Chrome’s profile button.

### Fixed

- Your Google profile picture didn’t show (you got a letter instead). Warden now understands every address style Google uses for profile pictures, and if Google’s account list has no picture it takes it from an open Google page.
- Without a picture, the button now shows the Google account’s own initial instead of the Warden space’s.

## 0.8.2 · Your Google accounts, clearer

*4 November 2026*

The account button now finds your Google sign-in reliably, and adding a second Gmail is one click.

### New

- "Add another Gmail account" in the account menu: it makes a separate space for the new Gmail (like a second Chrome profile, but in this window), opens Google’s sign-in there, and names the space after the account once you’re in. No form to fill in.
- The account menu lists every Gmail you’re signed in to, with its picture and email. Click one to open a tab signed in as that account.

### Fixed

- Updates downloaded but didn’t install when you closed Warden: Windows ended the little installer helper together with Warden. Updates now install through Windows Task Scheduler, the same way Chrome’s updater does, and the one-off task removes itself afterwards.
- The account button could say "Not signed in to Google" (and show no picture) while you were signed in. Warden now copes with changes in Google’s account list, and if that list still comes back empty it reads the account from an open Google page’s own avatar, the way Chrome does.

### Security

- The account check on Google pages runs in a separate, isolated space: the page’s own scripts can’t see it or feed it something else.
- Profile pictures are only fetched from Google’s own image servers.

## 0.8.1 · Testing automatic updates

*4 November 2026*

A test release for automatic updates. In 0.8.0 and 0.8.1 updates downloaded but didn’t install; 0.8.2 fixed that, and was tested end to end on a clean copy of Windows before release.

### Fixed

- When an update points somewhere other than Warden’s own releases, Settings → About now says exactly that, instead of "the update description was incomplete".

## 0.8.0 · Warden updates itself

*4 November 2026*

This is the last version you ever install by hand. From now on Warden downloads new versions in the background and installs them when you close it, then shows you this page.

### New

- Automatic updates. Warden checks for a new version a minute after it starts and every 4 hours, downloads it in the background, and installs it the next time you close Warden. It reopens exactly where you left off.
- "Restart to update" button by the address bar when an update is ready, if you don’t want to wait until you close Warden.
- Updates never cut off a film: if Warden Media (Netflix, Spotify…) is still open, the update waits until it’s closed too.
- This page. It opens by itself after every update and is always in Settings → About → What’s new.
- Settings → About shows the update status, a "Check now" button and a switch for automatic updates.
- Right-click the address bar for Cut, Copy, Paste, "Paste and go" and Select all, like in Chrome.

### Fixed

- You couldn’t copy the address from the address bar with the mouse: right-click did nothing.

### Security

- Every update is signed. Warden only installs an update whose description carries a valid signature from Warden’s private signing key, which never leaves the developer’s PC, and only if the downloaded installer matches that description’s SHA-256 fingerprint byte for byte. A hacked download server, a fake Wi-Fi network or a damaged download can’t get anything installed.
- Copying a password from Warden’s own password manager is supposed to clear it from the clipboard after 30 seconds. With the newer engine that check silently stopped working, so the password stayed on the clipboard. Fixed.
- No downgrades: Warden never installs a version older than the one it has, so an old, signed update with known bugs can’t be replayed.
- Updates download only from Warden’s own GitHub releases, without cookies, in a separate session that has nothing to do with your browsing.
- Engines checked today: main Warden runs Chromium 156.0.8078.80 (Electron 45.2.2, the newest Electron), Warden Media runs castlabs Electron 44.10.1 (castlabs’ newest). Google released Chrome 156.0.8078.88 on 3 November; Warden picks up those fixes as soon as Electron ships them, now automatically.

### What we looked up

- [How Chrome updates: a background service fetches new versions from Google’s servers and installs them on restart. Warden now works the same way, with GitHub as its update server.](https://support.google.com/chrome/answer/95414)
- [Electron’s releases, checked for a newer 45.x than 45.2.2 (none yet).](https://releases.electronjs.org/)
- [castlabs’ Electron releases, checked for a newer Widevine build than 44.10.1 (none yet).](https://github.com/castlabs/electron-releases/releases)
- [Chrome Releases blog: Google’s official list of each Chrome update’s security fixes.](https://chromereleases.googleblog.com/)

## 0.7.2 · Polish from an outside review

*4 November 2026*

Fixes for everything a second AI (Grok) found when it reviewed 0.7.0, plus safer password defaults.

### New

- Bitwarden is the pre-picked password manager in setup, and "Open Bitwarden when I finish" starts ticked. Picking Warden’s own manager shows a clear warning that Bitwarden is the safer choice.
- "Add login" in Settings → Passwords, for adding a login by hand to Warden’s own manager.
- When Defender flags a download, Warden shows the name Defender gave it and what that means: an automatic AI guess (often wrong about brand-new indie games), a "tool you might not want", or known malware. Guesses get a softer warning and a "Report a false positive" button.
- Plain HTTP sites now say "Not secure" in words next to the address.
- Lots of tabs: tabs keep a readable width and the tab strip scrolls, with fades at the edges when there are more. The close × is always faintly visible.

### Fixed

- Typing a file path (C:\… or file:///…) into the address bar sent it to your search engine as a search. Warden now refuses it and says why.
- Esc didn’t close the downloads panel and other popups.
- Setup’s Next and Back buttons jumped around between steps, and setup didn’t fit short windows. It’s now one fixed-size card that fits a 600-pixel-tall window.
- Setup’s artwork was cropped on some steps.
- Setup’s last screen now recaps your theme and password choice too.
- Importing passwords failed silently when Windows’ encryption wasn’t available. It now says so.
- A link that only downloads a file left an empty tab behind. That tab now closes by itself, like in Chrome.
- The "Scan downloads with Defender" switch looked on even on PCs without Defender.
- The Bitwarden window’s controls disappeared too quickly to find the close button. They now stay visible for a few seconds when it opens.

### Security

- Local file addresses are no longer leaked to your search engine.
- Bitwarden, an audited open-source password manager, is the default instead of Warden’s own unaudited one.

### What we looked up

- [Microsoft’s naming for Defender detections: names like Wacatac or Sabsik, or ones ending in !ml, are machine-learning guesses, the kind most often wrong about new software.](https://learn.microsoft.com/en-us/defender-xdr/malware-naming)
- [Microsoft’s form for reporting a file Defender got wrong.](https://www.microsoft.com/en-us/wdsi/filesubmission)

## 0.7.0 · A real installer and a proper welcome

*4 November 2026*

Warden Setup, a new eight-step first-run setup, and faster page opens.

### New

- Warden Setup.exe: a dark installer with Warden’s own artwork and a progress bar. It installs just for you with no admin prompt, adds Start-menu and desktop shortcuts and an Uninstall entry.
- Uninstalling asks before deleting your bookmarks and settings, and only removes Warden’s browser registration if it belongs to that copy.
- New first-run setup in eight short illustrated steps: welcome, bring your stuff from Chrome, Edge or Opera, Google sign-in, passwords, your games, look and protection, default browser (optional), and a summary. Every step can be skipped.
- Faster page opens: while you type in the address bar, arrow to a suggestion or hover a speed dial or bookmark, Warden connects to that site early (never to blocked or look-alike sites).
- Dragging a tab shows a see-through ghost exactly where it will land; drop on empty tab-bar space to send it to the end.
- The background texture is off by default, and much subtler if you turn it on.

### Fixed

- Warden Media now waits for Widevine on its very first start, instead of loading Netflix before protected video is ready.

### Security

- The installer never runs anything as administrator.

### What we looked up

- Measured why pages open a little slower than in Edge: Warden’s protections add almost nothing; the gap is the Electron engine itself. Early connections (preconnect) make up some of it.

## 0.6.1 · Tab dragging fix

*4 November 2026*

### Fixed

- Dropping a tab on the tab bar could land it one place off.

## 0.6.0 · Netflix, the safe way

*4 November 2026*

Streaming sites open in Warden Media, a separate copy signed for protected video, so the main Warden keeps all its security switches on.

### New

- Netflix, Spotify, Disney+, Prime Video and other streaming sites open in Warden Media, a separate window signed by castlabs for protected (Widevine) video. Type Netflix, click a Spotify link or open a Disney+ bookmark and it opens there; links out of it come back to the main Warden.
- Tabs keep their place across restarts: the second a video was at (paused if it was), back/forward history and scroll position. Warden saves it when you close it and every 2 minutes, so even a crash or power cut resumes close by.
- Drop a tab on another tab’s left half to go before it, right half to go after it.

### Fixed

- YouTube ads could slip through right after a restart, when pages loaded before the ad-block rules did. Pages now wait for the Shield (up to 20 seconds).
- The default browser check now reads where newer Windows 11 actually keeps the choice: no more false "links still open in Chrome".
- Background tabs could restart videos at 0:00 after a restart.

### Security

- Main Warden is back on the newest engine: Electron 45.2.2, Chromium 156.
- castlabs only signs an engine with its security switches (fuses) off, so that copy holds nothing but your streaming logins. Main Warden keeps all four switches on: it can’t be used as a script runner, can’t have code injected through environment variables, and keeps cookies encrypted on disk.
- Warden Media can’t download files and only gets the permissions protected video needs.

### What we looked up

- [Tested that castlabs’ signing service refuses an engine with the security switches on, which is why streaming lives in its own copy.](https://github.com/castlabs/electron-releases/wiki/EVS)

## 0.5.0 · Default browser, Bitwarden and security updates

*4 November 2026*

### New

- Warden registers itself with Windows as a browser, so it’s always listed in Settings → Default apps. It asks once (at most weekly, with "Don’t ask again") whether to become your default. Settings → General shows which browser is your default right now.
- Bitwarden opens in a small always-on-top window next to the page: the lock button in the toolbar, or Ctrl+Shift+L. Sign in once and it’s there for every Warden account.
- Security updates every two weeks: a scheduled check for new security releases of the engine, a rebuild and a test.
- First version with Widevine (protected video) support.

### What we looked up

- Tested Bitwarden’s Chrome extension in Electron: its background part crashes and its popup is blank, so Bitwarden’s own web vault is used instead.

## 0.4.0 · Accounts, sleep that remembers, Google sign-in

*4 November 2026*

### New

- Accounts: your dev, Reddit, YouTube and gaming logins in one Warden instead of five Chrome windows. Each has its own sign-ins, cookies and site data, sharing one engine so the memory overhead is paid once. Tabs show a coloured dot; right-click to move a tab or open a link in another account.
- Sleeping tabs keep your place: back/forward history, scroll position, typed text, and the video second (YouTube included). A tab with a half-written message is never auto-slept. Right-click a tab → Never sleep this site.
- Virus scan (Settings → Virus scan): drop files or folders, or scan Downloads, Desktop or any game’s folder, with Microsoft Defender.
- VPN (Settings → VPN): Warden’s traffic, not your games’, through your VPN provider’s proxy, with a kill switch, WebRTC and DNS kept inside it, per-account choice, and a live check of the address sites see.
- The RAM panel says why each tab is awake and splits Tabs from Warden itself; if your RAM cap can’t be met it tells you.

### Fixed

- Google sign-in: on first-party login pages (Google, Microsoft, Steam, Epic, Riot, Discord…) Warden now leaves the page untouched and looks exactly like regular Chrome, so Google accepts it.
- Passkey popups: both "sign in with a passkey" and "create a passkey?" requests now ask in Warden first; Windows’ passkey window only opens if you say yes.
- Game mode and the RAM cap didn’t work with YouTube open (its autoplay kept every tab "playing").

## 0.3.0 · Games, gamer safety and a real app

*3 November 2026*

### New

- Games tab (Ctrl+G): Steam, Xbox / Game Pass, Epic, Riot and Roblox games in one library with real cover art, Continue playing, Rediscover, Installed but never played, playtime, patch notes, PCGamingWiki settings tips and this week’s free Epic games.
- Play with Boost and automatic game mode: Warden sleeps its tabs, lowers its own CPU priority and pauses the wallpaper while you play.
- Sidecar windows: a small always-on-top window for a guide, map or stream, with opacity and click-through (Alt+Shift+C).
- Summon hotkey: Alt+Shift+W shows or hides Warden from anywhere.
- Warden’s own password manager with Windows encryption, exact-site filling and import from Chrome, Edge, Firefox, Bitwarden, 1Password, LastPass and Proton Pass.
- Safety checkup: Defender, Shield, HTTPS-only, encrypted DNS, and reused, weak or breached passwords.
- Address-bar autofill, search suggestions without cookies, switch-to-tab, per-site zoom, recently closed tabs, downloads history, a Settings search box, reorderable speed dials, real site logos, tray mode and crash recovery.
- Unread Gmail count on the taskbar icon and the account button.

### Fixed

- The RAM limit was silently broken.
- Importing and building the ad-block lists froze the window; they now run in the background.
- History lost visits when several tabs finished loading at the same moment.
- "Today" counters reset at 8 AM instead of midnight.
- Warden could open off-screen after unplugging a monitor.

### Security

- Gamer scam protection: Discord, Steam and free-skin phishing lists, ClickFix "paste this into Win+R" pages, fake login windows drawn inside a page, fake QR logins, clipboard hijacking (swapped wallet addresses and trade links), and cheats, cracks and injectors held in quarantine.
- Quarantine tabs: no downloads, no permissions, nothing saved.
- javascript: pasted into the address bar is refused (a Discord token-stealing trick).
- Look-alike scam sites get a "Go to the real site" button.
- Packaged as Warden.exe with Electron’s security fuses on.
- Settings, bookmarks, history and passwords keep a backup, so a power cut mid-save can’t wipe them.
- Upgraded to Electron 45.2.2 / Chromium 156.0.8078.80 for Chromium’s latest security fixes.

### What we looked up

- [The breached-password check uses Have I Been Pwned’s range lookup: only the first 5 characters of a scrambled fingerprint ever leave your PC.](https://haveibeenpwned.com/API/v3#PwnedPasswords)
- Six independent reviews (two security, two bug hunts, one on silent failures, one re-checking the fixes) plus a design review; everything they found was fixed and re-tested.

## 0.2 and earlier · Where Warden started

*2026-11*

### New

- A locked-down, ad-free Chromium browser built for leaving open while you game: the Shield (ads, trackers, malware and cookie banners blocked with EasyList, EasyPrivacy, uBlock Origin’s lists and more), sleeping tabs, a RAM budget, islands for grouping tabs, burner tabs, themes and wallpapers, and import from other browsers.

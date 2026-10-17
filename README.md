# Mixboat's Deadlock mod pages

This repo hosts the small web pages and the patch watch behind my Deadlock mods. Mods load these pages from
`mixboat.github.io/deadlock-mod-pages/...`.

Older mod releases use the same pages from the earlier repo, [Mixboat/wide-fov-slider](https://github.com/Mixboat/wide-fov-slider),
which stays online so those installs keep working. Both addresses are the same site, so they share the same saved notes.

## What's in here

| Path | What it is | Used by |
|---|---|---|
| [`shop-notes/`](shop-notes/) | **Shop Notes storage page.** Keeps your notes, templates, snapshots and pasted screenshots in the page's own browser storage (localStorage) on your PC. It also shows the box you paste screenshots into, in the notes' light or dark look. | [Shop Notes](https://gamebanana.com/mods/725094) and the notes in Seamless QoL |
| [`index.html`](index.html) | **Settings storage page.** Remembers small mod settings. | [Hide Investments](https://gamebanana.com/mods/724744) and the original [Wide FOV Slider](https://gamebanana.com/mods/724244) |
| [`violet-slide-song/`](violet-slide-song/) | **Violet Slide Song maker.** Open it in a normal browser, pick any song, choose the part that plays, and it builds a ready-to-install mod (`.vpk` in a zip) right in the page. Your song never leaves your computer. | Violet Slide Song (Flow State Soundtrack) |
| [`watch/`](watch/) + [`.github/workflows/`](.github/workflows/) | **Patch watch.** Every 6 hours, checks the latest Deadlock game files ([SteamTracking/GameTracking-Deadlock](https://github.com/SteamTracking/GameTracking-Deadlock)) for changes that would break a mod, and opens an issue when something changed. | Wide FOV Slider, Hide Investments, Old Damage Portraits, Shop Notes, Flow State Soundtrack |

## Privacy

- The storage pages run in a hidden in-game browser panel and only store data **in that panel's local storage on your own PC**.
- Nothing is sent anywhere, and the storage pages load nothing from other sites.
- The Violet Slide Song maker runs in your normal browser. It loads its mp3 encoder ([lamejs](https://github.com/zhuker/lamejs)) from jsDelivr and a monospace font from Google Fonts; the song you pick is processed in the page and never uploaded.
- Shop Notes keeps each Steam account's notes apart. Backups and template share codes contain only your note text, never your account id.

## How the mods talk to the page

Deadlock's UI scripts have no file or storage access of their own, so the mods load the page in a hidden panel. They send
requests in the page address (`#...`), and the page answers through its title. The Shop Notes page is versioned (now v6), and
every version answers older requests exactly as before, so older mod versions keep working.

## Credits

Thanks to **Predi** for the hidden storage-page technique these mods build on.
The Violet Slide Song maker encodes mp3s with [lamejs](https://github.com/zhuker/lamejs) (LGPL).

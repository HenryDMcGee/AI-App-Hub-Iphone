# Henry's AI Apps

An iPhone-style home screen that links to all of my projects in one place.

## What's on it

- **Home screen:** a Jira folder (CRM and Internship Watch boards), a GitHub folder (internship-watch, mccombs-course-planner, Resume-Website, Mars, plus a CRM repo placeholder), and a "Waiting…" tile for the CRM site
- **Dock:** Internship CRM, internship-watch, Public Job Board, and mcgeehenry.com

## Features

- **Phone view (default).** A tabby cat paw swipes "slide to open" on the lock screen, then the home screen opens inside a phone frame. Add `#full` to the URL to skip the intro and open the full-page view.
- **iOS-style editing.** Press and hold to make the icons jiggle, drag them between the home screen and the dock, or remove them with ⓧ. Reset Layout brings back the defaults.
- **Remembers your layout.** The layout and the music setting are saved in the browser's localStorage. Apps added to `ITEMS` in the code show up even for visitors who already rearranged their layout.
- **Background music.** An original J-pop-style loop (music box, koto-like plucks, wood block), generated in the browser with the Web Audio API and switched on or off with a toggle. The mew and latch sounds are also generated in code, with no audio files.
- **Generated wallpaper.** A deep-ocean gradient with soft bokeh light, drawn on a canvas.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole app in one self-contained page (markup, styles, script) |
| `hm-logo.png` | HM logo used for the website icons |
| `paw-tabby.webp` | Tabby paw used in the unlock animation |

## Adding an app

Add an entry to `ITEMS` in the script inside `index.html`, then place its id in `DEFAULT.home` or `DEFAULT.dock` (the dock holds up to 4).

```js
myapp: { kind: 'app', name: 'My App', href: 'https://example.com', c: 'site', g: 'globe' }
```

Kinds are `app` (a link), `folder` (has `kids`), and `waiting` (a placeholder with a progress bar).

## Running locally

It's a static page with no build step. Open `index.html` directly, or serve the folder:

```sh
python3 -m http.server 8000
```

Browsers only start the sound after the first tap or click.

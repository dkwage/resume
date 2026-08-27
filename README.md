# Resume — Minkoo Kang

A single-page resume site. One static `index.html`, no build step, no
JavaScript beyond the analytics snippet.

## Layout

```
index.html                       the whole page: content, plus style overrides in <head>
assets/css/devresume.css         theme stylesheet (vendor, unmodified)
assets/images/profile.webp       profile photo
assets/fontawesome/LICENSE.txt   licence for the inline icon paths
favicon/                         favicon set, shared with dkwage.com
favicon.ico                      legacy fallback
resume/                          source material (PDF, LaTeX), not referenced by the page
```

## Editing

Everything is in `index.html`. Sections in document order:

| Column | Sections |
|---|---|
| Main | Experiences, Research, Selected Projects |
| Sidebar | Education, Awards, Skills, Coursework, Leadership, Languages |

Each main-column entry is one `<div class="item mb-3">` block — copy an
existing block to add another. Two conventions worth keeping:

- In **Selected Projects**, `item-meta` holds the date only. The client or
  partner organization belongs in the first sentence of the body, where it
  reads as context rather than a label.
- In **Experiences**, `item-meta` holds `Organization | Mon. YYYY - Mon. YYYY`.

## Styling

`devresume.css` is vendor code and stays untouched. Every visual change is an
override in the `<style>` block at the top of `index.html`, in three groups:

- **Icons** — `.icon` sizing classes, since the FontAwesome runtime that used
  to inject them is gone
- **Accent** `#2c3e50`, matched to dkwage.com
- **Readability** — line height, reading measure capped at 1140px, and a phone
  pass (the theme's 0.4rem name tracking and 3rem card padding both overflow
  on small screens)

## Icons

Inline `<svg>`, not a font and not a script. The FontAwesome JS runtime was
removed; path data for the six icons in use came from Font Awesome Free. To add
one, copy its `viewBox` and `<path d="...">` and reuse the existing
`class="icon ..."` markup.

## Analytics

Google Analytics `G-S4V94NGWCK` — the same property as dkwage.com, so traffic
to both is reported together.

## Deploying

Static files, serve the directory as-is. On GitHub Pages, push to the branch
set as the Pages source. Locally:

```bash
python3 -m http.server
```

## Credits

Built on the **DevResume** template by
[Xiaoying Riley](https://themes.3rdwavemedia.com/) (3rd Wave Media). The theme
stylesheet is used unmodified, so the footer attribution link stays in place —
that is the condition the template is free under. Removing it requires a
commercial license from the theme website.

Icons from [Font Awesome Free](https://fontawesome.com/), licensed CC BY 4.0.
See `assets/fontawesome/LICENSE.txt`.

Resume content © Minkoo Kang.

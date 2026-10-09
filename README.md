# Link in Bio

A mobile-first [Masthead](https://masthead.site) theme for a personal link page: profile, links, featured work, social profiles and recent writing. Because it sits on a real Masthead site, it can grow into a blog or portfolio without moving anything.

Marketplace tags: `Personal`, `One-page`, `Minimal`.

## Setup

1. Pick the theme for the site.
2. **Pages → New page → Theme page → Link in Bio.** Fill in your profile and links, tick **Set as homepage**, then **Save & publish**. The checkbox needs Masthead ≥ 2.30.1; on older versions, set the homepage in Site settings.

Until a Link in Bio page is the homepage, `/` shows a fallback built from the site name, description, pages and posts, so the site never looks unfinished.

## Where things live

| What | Where | Why |
|---|---|---|
| Profile, links, socials, layout, recent writing | The **Link in Bio** page's settings | This is content. It survives a theme switch; theme settings don't. |
| Palette, light/dark, background, fonts, link style/shape/spacing, avatar shape, sharing image, footer | **Settings → Theme** (tokens) | This is appearance. It applies site-wide. |

### Layouts (page setting `layout`)

`classic list` · `grid` · `editorial` · `split` · `gallery` · `minimal text`

All six use the same markup; `data-layout` selects a CSS block in `theme.css`. You can switch at any time without losing content. Link style applies to the button layouts (classic list, grid, split); editorial, gallery and minimal text have their own treatment.

### Link kinds

- `link`: a button, with an optional thumbnail and description.
- `featured`: a large card with a cover image.
- `heading`: starts a new group.

Untick **Visible** to hide a link without deleting it.

### Palettes

`paper`, `ink`, `clay`, `moss` and `ultraviolet` each come in a light and a dark version. `appearance: auto` follows the visitor's system setting. `custom` uses the three custom colours in both modes. Filled buttons use the background colour for their text, so pick an accent that contrasts with your background.

Measured contrast (WCAG):

| Palette | Mode | Text | Muted | Accent on bg | Filled button |
|---|---|---|---|---|---|
| paper | light / dark | 15.3 / 15.6 | 6.4 / 7.0 | 4.6 / 8.1 | 4.6 / 8.1 |
| ink | light / dark | 15.8 / 15.8 | 6.6 / 7.0 | 5.9 / 7.6 | 5.9 / 7.6 |
| clay | light / dark | 13.6 / 14.8 | 5.9 / 6.7 | 6.0 / 8.8 | 6.0 / 8.8 |
| moss | light / dark | 13.9 / 15.2 | 5.9 / 6.8 | 6.0 / 11.2 | 6.0 / 11.2 |
| ultraviolet | light / dark | 15.2 / 15.8 | 6.4 / 6.9 | 6.2 / 7.9 | 6.2 / 7.9 |

## Notes for maintainers

- **URL guard.** Masthead doesn't check the scheme of `url` fields, so `bio.liquid` only renders `http(s)://`, `mailto:`, `tel:` and `/path` links; anything else is dropped. Socials allow `http(s)://` and `mailto:`.
- **No partials.** The link-item markup in `pages/bio.liquid` has a twin in `index.liquid`. Keep the two in step.
- **Social icons** are inline SVG from [Simple Icons](https://simpleicons.org) (CC0). LinkedIn, Email and Website are hand-drawn.
- **No JavaScript.** Fonts load from Google Fonts unless both font settings are `System …`.
- **Theme updates are live.** Re-uploading a newer version updates every site on the theme at once, so only make additive changes to the page and token schema.

## Develop

```sh
masthead preview            # http://localhost:4010, persona content in preview/
masthead preview --no-editor
masthead validate
masthead package
```

# Website integration: Parker Pierce cross-link and Spotify page

This branch adds a ready-to-serve static page at `music/index.html`, using the official Spotify artist embed and two verified individual track embeds, and adds a visible link at the top of the GitHub README.

## Connect the live duh.bet homepage

The currently connected repository does **not** contain the source of the homepage shown at `https://duh.bet/`. It has a `CNAME` file, but no homepage `index.html`, web app source, or site deployment workflow. Avoid replacing the existing homepage with a guessed copy.

In the **actual source of the live homepage**, add this small cross-project navigation immediately after the opening site header/nav. It mirrors the reciprocal "My Other Project" link at ParkerPierce.info:

```html
<div class="other-project-links" aria-label="Other projects">
  <a href="https://parkerpierce.info/" target="_blank" rel="noopener noreferrer">
    MY OTHER PROJECT: <strong>Parker Pierce ↗</strong>
  </a>
  <a href="/music/">LISTEN TO THE MUSIC ↗</a>
</div>
```

Optional unobtrusive styling, intended to inherit the site's existing text colors:

```css
.other-project-links {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  gap: .65rem 1.25rem;
  padding: .7rem 0;
  font-size: .78rem;
  letter-spacing: .07em;
  font-weight: 600;
}
.other-project-links a {
  color: inherit;
  text-decoration: none;
  border-bottom: 1px solid currentColor;
  padding-bottom: .15rem;
}
.other-project-links a:hover { opacity: .75; }
.other-project-links a:focus-visible {
  outline: 2px solid currentColor;
  outline-offset: 4px;
}
```

## Deployment notes

- Publish `music/index.html` at `https://duh.bet/music/` using whichever host currently serves duh.bet; merely adding files to this repository does **not** establish that the host deploys them.
- Ensure the existing site's security policy, if any, permits `frame-src https://open.spotify.com`.
- The page uses official Spotify iframes without a Spotify API key or custom JavaScript. Top tracks in the artist embed are managed by Spotify; they are not a frozen track list.
- Spotify embeds load third-party content. The music page provides direct Spotify links as a fallback.
- Leave the site's existing hero, applications, progress, build-with-us, and donation sections unchanged.

## Verified Spotify identifiers

- Artist: `3d7oUAqD0IDd3evYyKcHZP`
- SPARK · Live Studio Version: `1zv4x4EW0i9jm9CYRlYjTK`
- luv me 4 a min: `5PXvMLvKEv0Vb93RmWESTn`

The artist and both tracks were linked from `https://parkerpierce.info/` on November 7, 2026.

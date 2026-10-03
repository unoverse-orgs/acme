# Your project's styles

This folder restyles the whole design system for your brand — without editing a
single component. Three rules:

1. **Token NAMES are the contract, VALUES are yours.** Components reference names
   like `text.primary` and `action.primary`; you change what those names mean.
2. **Name a token to override it; omit it to inherit.** The cascade is per token,
   never per file. Never copy a whole file to change one line — the untouched lines
   would stop tracking platform improvements.
3. **Ingredients in `base/`, meaning in `themes/`.** `base/color.yaml` names your
   brand's raw colors (`color.brand.ink`); a theme file assigns them to roles
   (`text.primary: {color.brand.ink}`).

Start here:

- `base/color.yaml` — name your brand ingredients (a worked example is inside).
- Want your own theme? Copy the foundation's theme file whole — the ONE place
  copying is correct, because a theme must assign every role:
  https://github.com/unoverse-platform/marketplace/tree/main/definitions/styles/themes
  → save as `themes/light.yaml` here, then point roles at your `color.brand.*`.

Full guide: https://docs.unoverse.ai/design/styles-and-tokens.md

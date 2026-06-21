# Precipi Themes

A curated collection of VS Code themes by [precipi](https://precipi.com).
6 themes across 3 color families (Synthwave / Solar / Emerald), each in light & dark.

## Themes

| Theme | Type | Concept |
|-------|------|---------|
| Precipi Synthwave Light | Light | Daytime cyberpunk — neon purple & pink on a lavender canvas |
| Precipi Synthwave Dark | Dark | Nighttime cyberpunk — neon purple, pink & cyan on deep purple-navy |
| Precipi Solar Light | Light | Sunlight — vivid orange & amber on cream |
| Precipi Solar Dark | Dark | Sunlight — vivid orange & amber + cyan accents on a warm dark canvas |
| Precipi Emerald Light | Light | Fresh green — green & emerald + amber/cyan accents on mint cream |
| Precipi Emerald Dark | Dark | Fresh green — green & emerald + amber/cyan accents on deep green |

## Auto light/dark switching

To toggle, e.g. Solar Light ↔ Solar Dark automatically with your OS appearance,
add these lines to your user `settings.json` (`Ctrl+Shift+P` → *Preferences: Open User Settings (JSON)*):

```json
"window.autoDetectColorScheme": true,
"workbench.preferredLightColorTheme": "Precipi Solar Light",
"workbench.preferredDarkColorTheme": "Precipi Solar Dark"
```

Switching your OS light/dark mode (e.g. Windows Settings → Personalization → Colors) now switches the theme too.
Any pairing works — e.g. set `preferredDarkColorTheme` to `Precipi Synthwave Dark` or `Precipi Emerald Dark`.

> The extension never forces these settings (it respects your config). Enable it yourself only if you want auto-switching.

## License

MIT

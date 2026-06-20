# Precipi Themes

A curated collection of VS Code themes by [precipi](https://precipi.com).
6 themes across 3 color families (Synthwave / Solar / Emerald), each in light & dark.

## Themes

| Theme | Type | Concept |
|-------|------|---------|
| Precipi Synthwave Light | Light | Daytime cyberpunk — neon purple & pink on a lavender canvas / 낮의 사이버펑크 |
| Precipi Synthwave Dark | Dark | Nighttime cyberpunk — neon purple, pink & cyan on deep purple-navy / 밤의 사이버펑크 |
| Precipi Solar Light | Light | Sunlight — vivid orange & amber on cream / 햇살, 크림 배경 |
| Precipi Solar Dark | Dark | Sunlight — vivid orange & amber + cyan accents on warm dark / 햇살, 따뜻한 다크 배경 |
| Precipi Emerald Light | Light | Fresh green — green & emerald + amber/cyan accents on mint cream / 신록, 민트 크림 배경 |
| Precipi Emerald Dark | Dark | Fresh green — green & emerald + amber/cyan accents on deep green / 신록, 딥 그린 배경 |

## Installation

**Via Marketplace** (recommended)
1. Open Extensions (`Ctrl+Shift+X` / `Cmd+Shift+X`)
2. Search `Precipi Themes` → **Install**
3. Open the theme picker (`Ctrl+K Ctrl+T` / `Cmd+K Cmd+T`) → pick a theme

**Via GitHub Release**
1. Download the latest `precipi-themes-x.x.x.vsix` from the [Releases](https://github.com/shchun/precipi-vscode-themes/releases) page
2. Install with either:
   - CLI: `code --install-extension precipi-themes-x.x.x.vsix`
   - GUI: Extensions panel (`Ctrl+Shift+X`) → top-right `...` → **Install from VSIX...** → select the file
3. Theme picker (`Ctrl+K Ctrl+T` / `Cmd+K Cmd+T`) → pick a theme (restart VS Code if it doesn't apply)

**Via VSIX (local build)**
```bash
code --install-extension precipi-themes-x.x.x.vsix
```

## Auto light/dark switching / 라이트·다크 자동 전환

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

## Adding a New Theme

1. Add `themes/precipi-{name}-color-theme.json`
2. Add an entry to the `contributes.themes` array in `package.json`
3. Bump the version and package:
```bash
npm install -g @vscode/vsce
vsce package --no-dependencies
```

## Publishing

```bash
vsce login precipi
vsce publish
```

## License

MIT

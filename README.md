# Precipi Themes

A curated collection of VS Code themes by [precipi](https://precipi.com).

## Themes

| Theme | Type | Concept |
|-------|------|---------|
| Precipi Synthwave Light | Light | 낮의 사이버펑크 — 라벤더 배경에 네온 퍼플·핑크 |
| Precipi Ember Dark | Dark | 불꽃 — 흑갈색 배경에 몰튼 오렌지 |

## Installation

**Via Marketplace**
1. Extensions (`Ctrl+Shift+X` / `Cmd+Shift+X`)
2. Search `Precipi Themes` → Install
3. Theme picker (`Ctrl+K Ctrl+T` / `Cmd+K Cmd+T`) → 테마 선택

**Via VSIX**
```bash
code --install-extension precipi-themes-x.x.x.vsix
```

## Adding a New Theme

1. `themes/` 에 `precipi-{name}-color-theme.json` 추가
2. `package.json` → `contributes.themes` 배열에 항목 추가
3. 버전 올리고 패키징:
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

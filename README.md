# Precipi Themes

A curated collection of VS Code themes by [precipi](https://precipi.com).

## Themes

| Theme | Type | Concept |
|-------|------|---------|
| Precipi Synthwave Light | Light | 낮의 사이버펑크 — 라벤더 배경에 네온 퍼플·핑크 |
| Precipi Ember Dark | Dark | 불꽃 — 흑갈색 배경에 몰튼 오렌지 |
| Precipi Nixie Tube | Dark | Nixie 진공관 — 어두운 유리에 네온 앰버 글로우 + 수은증기 틸 악센트 |

## Installation

**Via Marketplace**
1. Extensions (`Ctrl+Shift+X` / `Cmd+Shift+X`)
2. Search `Precipi Themes` → Install
3. Theme picker (`Ctrl+K Ctrl+T` / `Cmd+K Cmd+T`) → 테마 선택

**Via GitHub Release**
1. [Releases](https://github.com/shchun/precipi-vscode-themes/releases) 페이지에서 최신 `precipi-themes-x.x.x.vsix` 다운로드
2. 아래 둘 중 하나로 설치:
   - CLI: `code --install-extension precipi-themes-x.x.x.vsix`
   - GUI: Extensions 패널(`Ctrl+Shift+X`) → 우측 상단 `...` → **Install from VSIX...** → 받은 파일 선택
3. Theme picker (`Ctrl+K Ctrl+T` / `Cmd+K Cmd+T`) → 테마 선택 (적용 안 되면 VS Code 재시작)

**Via VSIX (로컬 빌드)**
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

## vscode 터미널 꾸미기 (색)

세팅에 들어가서 workbench: color customizations 검색, settings.json 열기

내가 한 거 (workbench.colorCustomizations 추가)

색이 예뻐져서 터미널 로그 볼 때 기분이 좋다

```json
{
  "workbench.colorTheme": "Default Dark+",
  "editor.fontFamily": "D2Coding, Menlo, Monaco, 'Courier New', monospace",
  "window.zoomLevel": 1,
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "workbench.iconTheme": "eq-material-theme-icons-ocean",
  // color 세팅 
  "workbench.colorCustomizations": {
    "terminal.background": "#1D2021",
    "terminal.foreground": "#c7c7c7",
    "terminalCursor.background": "#be9cff",
    "terminalCursor.foreground": "#ffffff",
    "terminal.ansiBlack": "#575757",
    "terminal.ansiBlue": "#8d9cff",
    "terminal.ansiBrightBlack": "#676767",
    "terminal.ansiBrightBlue": "#bcc4ff",
    "terminal.ansiBrightCyan": "#9cfdff",
    "terminal.ansiBrightGreen": "#a4ffa9",
    "terminal.ansiBrightMagenta": "#ffb8e9",
    "terminal.ansiBrightRed": "#fa9797",
    "terminal.ansiBrightWhite": "#FDF4C1",
    "terminal.ansiBrightYellow": "#ffdc8a",
    "terminal.ansiCyan": "#a0f6f6",
    "terminal.ansiGreen": "#c0fec0",
    "terminal.ansiMagenta": "#ff9ee0",
    "terminal.ansiRed": "#ff9787",
    "terminal.ansiWhite": "#c7c7c7",
    "terminal.ansiYellow": "#fecb52"
  }
}
```

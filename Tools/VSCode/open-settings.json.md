## settings.json과 tabsize

### f1 - settings - Preferences: Open Settings (JSON)

- settings.json 여는 법

  - : vscode 좌측 하단 설정 클릭 or `ctrl/cmd + ,` 에서 setting으로 들어감 → 우측 상단에 open settings(JSON) 아이콘 클릭

    ![image](https://user-images.githubusercontent.com/76686872/204296532-b428a584-373e-4ab3-9fb0-709182592bdb.png)

  - F1 누른 후 `Preferences: Open User Settings (JSON)` 타이핑해서 찾아도 됨.

- 디폴트 tabsize는 "editor.tabSize" 속성으로 세팅

- 내 settings.json

  ```json
  // tabsize 수정함
  "editor.tabSize": 2,
  "[javascript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.tabSize": 2
  },
  "terminal.integrated.enableMultiLinePasteWarning": false,
  "editor.formatOnSave": true,
  "python.formatting.provider": "none",
  // typescript formatOnSave가 안 먹혀서 defaultFormatter 추가
  "[typescriptreact]": {
    // "editor.formatOnSave": true
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  }
  "[typescript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "javascript.updateImportsOnFileMove.enabled": "always",
  "bracket-pair-colorizer-2.depreciation-notice": false,
  "[python]": {
    "editor.formatOnPaste": true,
    "editor.tabSize": 4
  },
  ```

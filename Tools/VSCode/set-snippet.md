# VSCode에 스니펫 설정으로 빠른 코딩하기

cmd + shift + p 이후 Snippets: Configure User Snippets 선택 → New Global Snippets files → 파일명 지정 후 엔터 누르면 파일 생성됨

### 기본 설정 

```tsx
{
	// Place your global snippets here. Each snippet is defined under a snippet name and has a scope, prefix, body and 
	// description. Add comma separated ids of the languages where the snippet is applicable in the scope field. If scope 
	// is left empty or omitted, the snippet gets applied to all languages. The prefix is what is 
	// used to trigger the snippet and the body will be expanded and inserted. Possible variables are: 
	// $1, $2 for tab stops, $0 for the final cursor position, and ${1:label}, ${2:another} for placeholders. 
	// Placeholders with the same ids are connected.
	// Example:
	// "Print to console": {
	// 	"scope": "javascript,typescript",
	// 	"prefix": "log",
	// 	"body": [
	// 		"console.log('$1');",
	// 		"$2"
	// 	],
	// 	"description": "Log output to console"
	// }
}
```
### 요약
```tsx
"스니펫 이름": {
  "prefix": "단축키(입력할 글자)",
	// 실제 출력될 글자 
	// $1에는 커서가 첫번째로 위치함
  "body": "export const $1 = $2"
},
```

### 내 스니펫

```tsx
"Console log": {
    "prefix": "cl",
    "body": "console.log($1);",
    "description": "Log output to console"
  },
  "const": {
    "prefix": "con",
    "body": "const $1 = $2"
  },
  "Export const": {
    "prefix": "ec",
    "body": "export const $1 = $2"
  },
  "Export const styled": {
    "prefix": "ecs",
    "body": "export const $1 = styled.div`$2`;"
  },
  "import styled-components": {
    "prefix": "is",
    "body": "import styled from 'styled-components';"
  },
	"Story": {
    "prefix": "story",
    "body": [
      "import { ${TM_FILENAME/(.*).stories.tsx?/${1:/pascalcase}/} } from './${TM_FILENAME/(.*).stories.tsx?/${1}/}';",
      "",
      "export default {",
      "  title: '${1:${RELATIVE_FILEPATH/(.*).stories.tsx?/${1}/}}',",
      "  argTypes: {$2},",
      "};",
      "",
      "export const ${TM_FILENAME/(.*).stories.tsx?/${1:/pascalcase}/}Story: React.FC<any> = (args) => (",
      "  <${TM_FILENAME/(.*).stories.tsx?/${1:/pascalcase}/} {...args} />",
      ");"
    ]
  },
	"python sys input": {
    "scope": "python",
    "prefix": "sinput",
    "body": ["import sys", "input = sys.stdin.readline", "", ""]
  }
```

---
참고  
- [Snippets in Visual Studio Code](https://code.visualstudio.com/docs/editor/userdefinedsnippets)  
- [코딩 빠르게 하는 꿀팁 및 설정](https://www.youtube.com/watch?v=umeqCopb96w&list=LL&index=2)  
- [storybook vscode helper](https://github.com/riccardo-forina/storybook-vscode-helper/blob/main/snippets/typescript.json)

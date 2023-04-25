# Configurações do VSCode

<details open>
<summary><b>Tabela de conteúdos</b></summary>

- [Shortcuts customizados](#shortcuts-customizados)
- [Extensões](#extensões)
- [Arquivo de configurações](#arquivo-de-configurações)
</details>

## Shortcuts customizados
Abre este arquivo buscando por "Open Keyboard Shortcuts (JSON)"
- ```n``` - Cria um novo arquivo ao estar no navegador de arquivos
- ```ctrl + shift + g``` - Abre o Git Graph
```json
[
    {
        "key": "n",
        "command": "explorer.newFile",
        "when": "explorerViewletVisible && filesExplorerFocus && !explorerResourceReadonly && !inputFocus"
    },
    {
        "key": "ctrl+shift+g",
        "command": "git-graph.view"
    }
]
```
{
  "key": "n",
  "command": "explorer.newFile",
  "when": "explorerViewletVisible && filesExplorerFocus && !explorerResourceReadonly && !inputFocus"
}

## Extensões
- [WSL](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl) - Suporte para o WSL
- [DotENV](https://marketplace.visualstudio.com/items?itemName=mikestead.dotenv) - Suporte para arquivos .env
- [ENV](https://marketplace.visualstudio.com/items?itemName=IronGeek.vscode-env) - Faz o highlight nos arquivos .env
- [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - Verifica a ortografia do código
- [EditorConfig for VS Code](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig) - Suporte para o arquivo .editorconfig
- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) - Suporte para o ESLint
- [Git Graph](https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph) - Mostra a arvore de elementos do Git
- [GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot) - IA para programar
- [Error Lens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens) - Mostra erros e avisos inline no código
- [Console Ninja](https://marketplace.visualstudio.com/items?itemName=WallabyJs.console-ninja) - Mostra o console.log inline no código
- [Import Cost](https://marketplace.visualstudio.com/items?itemName=wix.vscode-import-cost) - Mostra o tamanho do pacote importado inline no código
- [Live Share](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare) - Compartilhamento de código em tempo real
- [Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag) - Renomeia a tag de fechamento quando a tag de abertura é renomeada
- [Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss) - Suporte para o Tailwind CSS
- [Sorcerer](https://marketplace.visualstudio.com/items?itemName=MarkThomasMiller.sorcerer) - Tema dark do VSCode
- [GlassIt-VSC](https://marketplace.visualstudio.com/items?itemName=s-nlf-fh.glassit) - Deixa o VSCode transparente
- [Material Icon Theme](https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme) - Ícones para arquivos e pastas
- [Prisma](https://marketplace.visualstudio.com/items?itemName=Prisma.prisma) - Suporte para o Prisma
- [Prisma Insider](https://marketplace.visualstudio.com/items?itemName=Prisma.prisma-insider) - Versão beta do Prisma
- [PHP Intelephense](https://marketplace.visualstudio.com/items?itemName=bmewburn.vscode-intelephense-client) - Suporte para PHP

## Arquivo de configurações
```json
{
  // VS Code
  "workbench.startupEditor": "newUntitledFile",
  "workbench.editor.labelFormat": "short",
  "workbench.iconTheme": "material-icon-theme",
  "editor.rulers": [100],
  "editor.fontSize": 18,
  "editor.lineHeight": 26,
  "editor.fontFamily": "Fira Code",
  "editor.fontWeight": 500,
  "editor.fontLigatures": true,
  "editor.wordWrap": "off",
  "editor.semanticHighlighting.enabled": false,
  "editor.formatOnSave": false,
  "editor.renderLineHighlight": "gutter",
  "editor.parameterHints.enabled": false,

  // Auto fix on save
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true,
    // "source.fixAll": true,
    "source.organizeImports": false
  },

  // Terminal
  "terminal.integrated.fontSize": 16,
  "terminal.integrated.fontWeight": "500",
  "terminal.integrated.fontFamily": "Fira Code",
  "terminal.integrated.showExitAlert": false,

  "explorer.compactFolders": false,
  "extensions.ignoreRecommendations": true,
  "breadcrumbs.enabled": true,
  "explorer.confirmDragAndDrop": true,
  "explorer.confirmDelete": true,
  "files.exclude": {
    "**/.git": true,
    "**/.husky": true,
    "**/.svn": true,
    "**/.hg": true,
    "**/.CVS": true,
    "**/.DS_Store": true,
    "**/.next": true,
    "**/node_modules": true
  },
  "files.associations": {
    ".sequilizerc": "javascript",
    ".stylelintrc": "json",
    ".prettierrc": "json",
    ".tsx": "typescriptreact",
    ".env.*": "dotenv",
    "*.css": "css",
    "css": "css"
  },
  "emmet.syntaxProfiles": {
    "javascript": "jsx"
  },
  "emmet.includeLanguages": {
    "javascript": "javascriptreact"
  },
  "git.enableSmartCommit": true,
  "typescript.tsserver.log": "off",
  "javascript.suggest.autoImports": true,
  "typescript.suggest.autoImports": true,
  "material-icon-theme.activeIconPack": "nest",
  "screencastMode.onlyKeyboardShortcuts": true,
  "material-icon-theme.folders.associations": {
    "infra": "app",
    "entities": "class",
    "domain": "class",
    "schemas": "class",
    "typeorm": "database",
    "repositories": "mappings",
    "http": "container",
    "migrations": "tools",
    "modules": "components",
    "implementations": "core",
    "dtos": "typescript",
    "fakes": "mock",
    "websockets": "pipe",
    "protos": "pipe",
    "grpc": "pipe",
    "providers": "include",
    "subscribers": "messages",
    "useCases": "controller",
    "kafka": "scripts",
    "mappers": "meta",
    "_shared": "shared",
    "eslint-config": "tools",
    "kube": "kubernetes"
  },
  "material-icon-theme.files.associations": {
    "ormconfig.json": "database",
    "tsconfig.json": "tune",
    "*.proto": "3d",
    "*.webpack.js": "webpack"
  },
  "material-icon-theme.languages.associations": {
    "dotenv": "tune"
  },
  "typescript.updateImportsOnFileMove.enabled": "always",
  "javascript.updateImportsOnFileMove.enabled": "always",
  "editor.suggestSelection": "recentlyUsed",
  "[typescript]": {
    "editor.defaultFormatter": "vscode.typescript-language-features"
  },
  "[typescriptreact]": {
    "editor.defaultFormatter": "vscode.typescript-language-features"
  },
  "bracketPairColorizer.depreciation-notice": false,
  "cSpell.language": "pt_BR, pt, en",
  "cSpell.userWords": ["Chakra", "chakra"],
  "[prisma]": {
    "editor.formatOnSave": true,
    "editor.defaultFormatter": "Prisma.prisma"
  },
  "editor.inlineSuggest.enabled": true,
  "diffEditor.codeLens": true,
  "editor.suggest.localityBonus": true,
  "editor.suggest.preview": true,
  "editor.suggest.shareSuggestSelections": true,
  "editor.suggest.showStatusBar": true,
  "files.autoGuessEncoding": true,
  "files.insertFinalNewline": true,
  "files.simpleDialog.enable": true,
  "editor.minimap.enabled": false,
  "[jsonc]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "workbench.colorTheme": "Sorcerer",
  "liveServer.settings.donotShowInfoMsg": true,
  "workbench.sideBar.location": "right",
  "workbench.editor.showTabs": false,
  "workbench.colorCustomizations": {
    "editor.lineHighlightBackground": "#000", // Line highlight - bg
    "editorLineNumber.activeForeground": "#FFF", // Line highlight - color
    "editor.lineHighlightBorder": "#ff006a", // Line highlight - border
    "focusBorder": "#ff006a", // Sidebar - border focus selected
    "editorCursor.foreground": "#FFF" // Cursor
  },
  "glassit.alpha": 200,
  "[html]": {
    "editor.defaultFormatter": "vscode.html-language-features"
  },
  "tabnine.experimentalAutoImports": true,
  "workbench.editor.untitled.hint": "hidden",
  "totalTypeScript.hideAllTips": false,
  "totalTypeScript.hideBasicTips": true,
  "totalTypeScript.hiddenTips": [
    "passing-generics-to-types",
    "omit-utility-type",
    "pick-utility-type"
  ],
  "terminal.integrated.env.linux": {},
  "github.copilot.enable": {
    "*": true,
    "yaml": false,
    "plaintext": false,
    "markdown": true
  },
  "window.menuBarVisibility": "compact"
}
```

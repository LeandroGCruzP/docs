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
- Retirando bind de abrir Github Copilot com ```ctrl + enter```
- ```ctrl + shift + .``` - Abre Github Copilot

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
    },
    {
        "key": "ctrl+enter",
        "command": "-github.copilot.generate",
        "when": "editorTextFocus && github.copilot.activated && !inInteractiveInput && !interactiveEditorFocused"
    },
    {
        "key": "ctrl+shift+oem_period",
        "command": "github.copilot.generate",
        "when": "editorTextFocus && github.copilot.activated && !inInteractiveInput && !interactiveEditorFocused"
    },
]
```

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
- [FiraCode font - Professional Font for Developers](https://marketplace.visualstudio.com/items?itemName=SeyyedKhandon.firacode) - Font ligatures

## Arquivo de configurações
```json
{
    "editor.fontSize": 16, // Font size
    "editor.lineHeight": 24, // Line height
    "editor.fontWeight": 500, // Font weight
    "editor.fontFamily": "Fira Code", // Font family
    "editor.fontLigatures": true, // Font ligatures
    "editor.inlineSuggest.enabled": true, // Show logs and error inline
    "terminal.integrated.env.windows": {},
    "workbench.colorTheme": "Sorcerer", // Theme editor
    "workbench.iconTheme": "material-icon-theme", // Theme icons
    "glassit.alpha": 240, // Opacity window
    "editor.formatOnSave": true, // Format code on save
    "editor.codeActionsOnSave": { // Fix code on save
        "source.fixAll.eslint": true,
        "source.organizeImports": true
    },
    "terminal.integrated.fontSize": 16, // Font size terminal
    "terminal.integrated.fontWeight": "500", // Font weight terminal
    "terminal.integrated.fontFamily": "Fira Code", // Font family terminal
    "files.exclude": { // Hide files and folders
        "**/.git": true,
        "**/.next": true,
        "**/node_modules": true,
    },
    "editor.minimap.enabled": false, // Minimap visibility
    "window.menuBarVisibility": "hidden", // Menu bar visibility
    "workbench.layoutControl.enabled": false, // Layout control visibility 
    "workbench.activityBar.visible": false, // Sidebar visibility 
    "workbench.sideBar.location": "right", // Sidebar position
    "workbench.statusBar.visible": false, // Status bar visibility
    "workbench.editor.showTabs": false, // Tabs visibility
    "editor.scrollbar.vertical": "hidden", // Vertical scrollbar visibility
    "editor.overviewRulerBorder": false, // Vertical scrollbar border visibility
    "editor.hideCursorInOverviewRuler": true, // Breadcrumbs visibility
    // "breadcrumbs.enabled": false, // Breadcrumbs visibility
    "editor.glyphMargin": false, // Glyph margin visibility
    "workbench.colorCustomizations": {
        "editor.lineHighlightBorder": "#ff000000", // Line document highlight border color
        "focusBorder": "#ff006a", // Sidebar border focus selected color
        "editorLineNumber.activeForeground": "#FFF", // Line number color
        "editorCursor.foreground": "#FFF", // Cursor color
    },
    "terminal.integrated.env.linux": {}, // Environment variables
}
```

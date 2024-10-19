# Visual Studio Code Setting

[top page](./README.md)

<br>

## Contents

* [方針](#方針)
* [Keybind Setting](#keybind-setting)
* [Code Runner Setting](#code-runner-setting)
* [VSCode Vim Setting](#vscode-vim-setting)

<br>

## 方針

エディタ上ではVimのキーバインドを使用し、そのほかは基本的にはVSCodeのデフォルトキーバインドを使用する。

<br>

## Keybind Setting

```json
// Place your key bindings in this file to override the defaults
[
    // コマンドパレット等でj移動
    {
        "key": "ctrl+j",
        "command": "workbench.action.quickOpenSelectNext",
        "when": "inQuickOpen"
    },
    // コマンドパレット等でk移動
    {
        "key": "ctrl+k",
        "command": "workbench.action.quickOpenSelectPrevious",
        "when": "inQuickOpen"
    },
    // Easy navigation in suggestion/intellisense
    // Cannot be added to package.json because of conflict with vim's default bindings
    {
        "key": "ctrl+j",
        "command": "selectNextSuggestion",
        "when": "suggestWidgetMultipleSuggestions && suggestWidgetVisible && textInputFocus"
    },
    {
        "key": "ctrl+k",
        "command": "selectPrevSuggestion",
        "when": "suggestWidgetMultipleSuggestions && suggestWidgetVisible && textInputFocus"
    },
    {
        "key": "ctrl+l",
        "command": "acceptSelectedSuggestion",
        "when": "suggestWidgetMultipleSuggestions && suggestWidgetVisible && textInputFocus"
    },
    // Easy navigation in code action
    {
        "key": "ctrl+j",
        "command": "selectNextCodeAction",
        "when": "codeActionMenuVisible"
    },
    {
        "key": "ctrl+k",
        "command": "selectPrevCodeAction",
        "when": "codeActionMenuVisible"
    },
    {
        "key": "ctrl+l",
        "command": "acceptSelectedCodeAction",
        "when": "codeActionMenuVisible"
    },
    // Add ctrl+h/l to navigate in file browser
    {
        "key": "ctrl+h",
        "command": "file-browser.stepOut",
        "when": "inFileBrowser"
    },
    {
        "key": "ctrl+l",
        "command": "file-browser.stepIn",
        "when": "inFileBrowser"
    },
    // Easy navigation in parameter hint (i.e. traverse the hints when there's multiple overload for one method)
    // Cannot be added to package.json because of conflict with vim's default bindings
    {
        "key": "ctrl+j",
        "command": "showNextParameterHint",
        "when": "editorFocus && parameterHintsMultipleSignatures && parameterHintsVisible"
    },
    {
        "key": "ctrl+k",
        "command": "showPrevParameterHint",
        "when": "editorFocus && parameterHintsMultipleSignatures && parameterHintsVisible"
    },
    // サジェストのキャンセル
    {
        "key": "ctrl+[",
        "command": "settings.action.clearSearchResults",
        "when": "inSettingsSearch"
    },
    // サジェストのキャンセル
    {
        "key": "ctrl+[",
        "command": "keybindings.editor.clearSearchResults",
        "when": "inKeybindings && inKeybindingsSearch"
    },
    // # Seetings for VSpaceCode
    // Trigger vspacecode in empty editor group
    {
        "key": "space",
        "command": "vspacecode.space",
        "when": "activeEditorGroupEmpty && focusedView == '' && !whichkeyActive && !inputFocus"
    },
    // Trigger vspacecode when sidebar is in focus
    {
        "key": "space",
        "command": "vspacecode.space",
        "when": "sideBarFocus && !inputFocus && !whichkeyActive"
    },
    {
        "key": "ctrl+space",
        "command": "ibmcuratorAI.sourceCodeFromComments",
    },
    // "Quick Window Navigation" settings described in "Bonus" section (https://vspacecode.github.io/docs/bonus#quick-window-navigation)
    {
        "key": "ctrl+h",
        "command": "workbench.action.navigateLeft",
        "when": "!inQuickOpen && !suggestWidgetVisible && !parameterHintsVisible && !isInDiffEditor"
    },
    {
        "key": "ctrl+j",
        "command": "workbench.action.navigateDown",
        "when": "!codeActionMenuVisible && !inQuickOpen && !suggestWidgetVisible && !parameterHintsVisible"
    },
    {
        "key": "ctrl+k",
        "command": "workbench.action.navigateUp",
        "when": "!codeActionMenuVisible && !inQuickOpen && !suggestWidgetVisible && !parameterHintsVisible"
    },
    {
        "key": "ctrl+l",
        "command": "workbench.action.navigateRight",
        "when": "!codeActionMenuVisible && !inQuickOpen && !suggestWidgetVisible && !parameterHintsVisible && !isInDiffEditor"
    },
    // Quick Navigation for diff view
    {
        "key": "ctrl+h",
        "command": "workbench.action.compareEditor.focusSecondarySide",
        "when": "isInDiffEditor && !isInDiffLeftEditor"
    },
    {
        "key": "ctrl+h",
        "command": "workbench.action.navigateLeft",
        "when": "isInDiffEditor && isInDiffLeftEditor"
    },
    {
        "key": "ctrl+l",
        "command": "workbench.action.compareEditor.focusPrimarySide",
        "when": "isInDiffEditor && isInDiffLeftEditor"
    },
    {
        "key": "ctrl+l",
        "command": "workbench.action.navigateRight",
        "when": "isInDiffEditor && !isInDiffLeftEditor"
    },
    // Disable default keybind when focusing a terminal for terminal emulator
    {
        "key": "ctrl+f",
        "command": "",
        "when": "terminalFocus"
    },
    {
        "key": "ctrl+e",
        "command": "",
        "when": "terminalFocus"
    },
    {
        "key": "ctrl+p",
        "command": "",
        "when": "terminalFocus"
    },
    // # Seetings for VSpaceCode
    // Trigger vspacecode in empty editor group
    {
        "key": "ctrl+space",
        "command": "vspacecode.space",
        "when": "terminalFocusInAny"
    },
]
```

<br>

## Code Runner Setting

```json
"code-runner.clearPreviousOutput": true,

"code-runner.executorMap": {
    "javascript": "node",
    "java": "cd $dir && javac \"-J-Duser.language=en\" \"-J-Dfile.encoding=UTF-8\" $fileName && java \"-Duser.language=en\" \"-J-Dfile.encoding=UTF-8\" $fileNameWithoutExt",
    "c": "cd $dir && gcc $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt",
    "cpp": "cd $dir && g++ $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt",
    "objective-c": "cd $dir && gcc -framework Cocoa $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt",
    "php": "php",
    "python": "python -u",
    "perl": "perl",
    "perl6": "perl6",
    "ruby": "ruby",
    "go": "go run",
    "lua": "lua",
    "groovy": "groovy",
    "powershell": "powershell -ExecutionPolicy ByPass -File",
    "bat": "cmd /c",
    "shellscript": "bash",
    "fsharp": "fsi",
    "csharp": "dotnet run $fileName",
    "vbscript": "cscript //Nologo",
    "typescript": "ts-node",
    "coffeescript": "coffee",
    "scala": "scala",
    "swift": "swift",
    "julia": "julia",
    "crystal": "crystal",
    "ocaml": "ocaml",
    "r": "Rscript",
    "applescript": "osascript",
    "clojure": "lein exec",
    "haxe": "haxe --cwd $dirWithoutTrailingSlash --run $fileNameWithoutExt",
    "rust": "cd $dir && rustc $fileName && $dir$fileNameWithoutExt",
    "racket": "racket",
    "scheme": "csi -script",
    "ahk": "autohotkey",
    "autoit": "autoit3",
    "dart": "dart",
    "pascal": "cd $dir && fpc $fileName && $dir$fileNameWithoutExt",
    "d": "cd $dir && dmd $fileName && $dir$fileNameWithoutExt",
    "haskell": "runhaskell",
    "nim": "nim compile --verbosity:0 --hints:off --run",
    "lisp": "sbcl --script",
    "kit": "kitc --run",
    "v": "v run",
    "sass": "sass --style expanded",
    "scss": "scss --style expanded",
    "less": "cd $dir && lessc $fileName $fileNameWithoutExt.css",
    "FortranFreeForm": "cd $dir && gfortran $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt",
    "fortran-modern": "cd $dir && gfortran $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt",
    "fortran_fixed-form": "cd $dir && gfortran $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt",
    "fortran": "cd $dir && gfortran $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt"
}
```

<br>

## Font Setting

```json
    // FONT設定
    "editor.fontFamily": "'IBM Plex Mono', 'IBM Plex Sans JP'",
    "terminal.integrated.fontFamily": "'IBM Plex Mono', 'IBM Plex Sans JP'",
```

<br>

## VSCode Vim Setting

```json
    // vim設定
    // vim用 setting
    "editor.wordWrap": "on", // 改行を折り返して表示
    "files.trimTrailingWhitespace": true, // 保存時whitespaceのみを削除
    "editor.minimap.enabled": false, // 右サイドのミニマップを非表示

    // vim setting
    "vim.easymotion": true, // easymotion有効化
    "vim.hlsearch": true, // 検索をハイライト
    "vim.incsearch": true, // 複数の検索結果をハイライト
    "vim.visualstar": true, // カーソルがあるワードを*で検索
    "vim.useSystemClipboard": true, // Yunk等をシステムのクリップボードにコピー
    "vim.useCtrlKeys": true, // vimのCtrlキーコマンドを有効化
    "vim.insertModeKeyBindings": [
        {
            "before": ["j", "j"],
            "after": ["<Esc>"]
        },
    ],
    "vim.normalModeKeyBindingsNonRecursive": [
        {
            "before": ["<space>"],
            "commands": ["vspacecode.space"]
        },
        {
            "before": [","],
            "commands": [
                "vspacecode.space",
                {
                    "command": "whichkey.triggerKey",
                    "args": "m"
                }
            ]
        },
        {
            "before": ["<leader>", "d"],
            "after": ["d", "d"]
        },
        {
            "before": ["<C-n>"],
            "commands": [":nohl"]
        },
        {
            "before": ["x"],
            "after": ["\"", "_", "x"]
        },
        {
            "before": ["s"],
            "after": ["\"", "_", "s"]
        },
        {
            "before": ["u"],
            "commands": ["undo"]
        },
        {
            "before": ["<C-r>"],
            "commands": ["redo"]
        },
    ],
    "vim.visualModeKeyBindingsNonRecursive": [
        {
            "before": ["<space>"],
            "commands": ["vspacecode.space"],
        },
        {
            "before": [","],
            "commands": [
                "vspacecode.space",
                {
                    "command": "whichkey.triggerKey",
                    "args": "m"
                }
            ]
        },
        {
            "before": [">"],
            "commands": ["editor.action.indentLines"],
        },
        {
            "before": ["<"],
            "commands": ["editor.action.outdentLines"],
        },
    ],
```

<br>

## VSpaceCode Setting

```json
    "vspacecode.bindingOverrides": [
        {
            "keys": "f.@",
            "name": "Create terminal in editor area",
            "type": "command",
            "command": "workbench.action.createTerminalEditor",
        }
    ],
```

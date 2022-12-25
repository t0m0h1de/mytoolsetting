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
    // サジェスト内でj移動
    {
        "key": "ctrl+j",
        "command": "selectNextSuggestion",
        "when": "suggestWidgetMultipleSuggestions && suggestWidgetVisible && textInputFocus"
    },
    // サジェスト内でk移動
    {
        "key": "ctrl+k",
        "command": "selectPrevSuggestion",
        "when": "suggestWidgetMultipleSuggestions && suggestWidgetVisible && textInputFocus"
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
    }
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

## VSCode Vim Setting

```json
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
            "before" : ["u"],
            "commands" : ["undo"]
        },
        {
            "before" : ["<C-r>"],
            "commands" : ["redo"]
        },
    ],
```

# My Tool Setting

---

<br>

## Windows Terminal Action Setting

| Action | key |
| --- | --- |
| コピー | ctrl + shift + c |
| ペースト | ctrl + shift + v |
| 検索 | ctrl + shift + f |
| タブを閉じる | alt + shift + q |
| ペインを閉じる | alt + q |
| タブを複製する | alt + ctrl + t |
| コマンドパレット | F1 |
| 横にペイン分け(複製) | alt + ctrl + h |
| 自動ペイン分け(複製) | alt + ctrl + d |
| 縦にペイン分け(複製) | alt + ctrl + v |
| 上にフォーカス | alt + k |
| 左にフォーカス | alt + h |
| 右にフォーカス | alt + l |
| 下にフォーカス | alt + j |
| 上にリサイズ | alt + shift + k |
| 左にリサイズ | alt + shift + h |
| 右にリサイズ | alt + shift + l |
| 下にリサイズ | alt + shift + j |

<br> 

```
    "actions":
    [
        {
            "command":
            {
                "action": "copy",
                "singleLine": false
            },
            "keys": "ctrl+shift+c"
        },
        {
            "command": "paste",
            "keys": "ctrl+shift+v"
        },
        {
            "command": "find",
            "keys": "ctrl+shift+f"
        },
        {
            "command": "closeTab",
            "keys": "alt+shift+q"
        },
        {
            "command": "closePane",
            "keys": "alt+q"
        },
        {
            "command": "duplicateTab",
            "keys": "ctrl+alt+t"
        },
        {
            "command":
            {
                "action": "commandPalette"
            },
            "keys": "f1"
        },
        {
            "command":
            {
                "action": "splitPane",
                "split": "horizontal",
                "splitMode": "duplicate"
            },
            "keys": "alt+ctrl+h"
        },
        {
            "command":
            {
                "action": "splitPane",
                "split": "auto",
                "splitMode": "duplicate"
            },
            "keys": "alt+ctrl+d"
        },
        {
            "command":
            {
                "action": "splitPane",
                "split": "vertical",
                "splitMode": "duplicate"
            },
            "keys": "alt+ctrl+v"
        },
        {
            "command":
            {
                "action": "moveFocus",
                "direction": "up"
            },
            "keys": "alt+k"
        },
        {
            "command":
            {
                "action": "moveFocus",
                "direction": "left"
            },
            "keys": "alt+h"
        },
        {
            "command":
            {
                "action": "moveFocus",
                "direction": "right"
            },
            "keys": "alt+l"
        },
        {
            "command":
            {
                "action": "moveFocus",
                "direction": "down"
            },
            "keys": "alt+j"
        },
        {
            "command":
            {
                "action": "resizePane",
                "direction": "up"
            },
            "keys": "alt+shift+k"
        },
        {
            "command":
            {
                "action": "resizePane",
                "direction": "left"
            },
            "keys": "alt+shift+h"
        },
        {
            "command":
            {
                "action": "resizePane",
                "direction": "right"
            },
            "keys": "alt+shift+l"
        },
        {
            "command":
            {
                "action": "resizePane",
                "direction": "down"
            },
            "keys": "alt+shift+j"
        }
    ],
```

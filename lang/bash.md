# Bash

> 浓缩 https://wangdoc.com/bash/intro

## 快捷键

- `Ctrl + L`：清除屏幕并将当前行移到页面顶部。
- `Ctrl + C`：中止当前正在执行的命令。
- `Shift + PageUp`：向上滚动。
- `Shift + PageDown`：向下滚动。
- `Ctrl + U`：从光标位置删除到行首。
- `Ctrl + K`：从光标位置删除到行尾。
- `Ctrl + W`：删除光标位置前一个单词。
- `Ctrl + D`：关闭 Shell 会话。
- `↑`，`↓`：浏览已执行命令的历史记录。

## 模式扩展 globbing | wildcard expansion

- `~` 用户目录
- `?` 单个字符
- `*` 任意个字符
- `[...]` 匹配之中任意一个字符，例如匹配数字 `[0123456789]`，也可以 `[0-9]`，否定形式 `[!0-9]`
- `{...}` 扩展每个字符， `echo {1,2,3}` → `1 2 3`，也可以`{1..3}`，支持逆向 `{3..1}`，可以嵌套
- `${..}` 变量扩展，`${!string*}` 或 `${!string@}` 返回所有匹配给定字符串 string 的变量名
- `$(..)` 子命令扩展，`$(date)`
- `$((..))` 算数扩展，`$((1 + 1))`
- `[[:class:]]` 表示一个字符类，否定 `[![:class:]]`
  - `[[:alnum:]]` 匹配任意英文字母与数字
  - `[[:alpha:]]` 匹配任意英文字母
  - `[[:blank:]]` 空格和 Tab 键
  - `[[:cntrl:]]` ASCII 码 0-31 的不可打印字符
  - `[[:digit:]]` 匹配任意数字 0-9
  - `[[:graph:]]` A-Z、a-z、0-9 和标点符号
  - `[[:lower:]]` 匹配任意小写字母 a-z
  - `[[:print:]]` ASCII 码 32-127 的可打印字符
  - `[[:punct:]]` 标点符号（除了 A-Z、a-z、0-9 的可打印字符）
  - `[[:space:]]` 空格、Tab、LF（10）、VT（11）、FF（12）、CR（13）
  - `[[:upper:]]` 匹配任意大写字母 A-Z
  - `[[:xdigit:]]` 16进制字符（A-F、a-f、0-9）

量词语法

- `?(pattern-list)` 模式匹配零次或一次
- `*(pattern-list)` 模式匹配零次或多次
- `+(pattern-list)` 模式匹配一次或多次
- `@(pattern-list)` 只匹配一次模式
- `!(pattern-list)` 匹配给定模式以外的任何内容

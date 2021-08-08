# VS Code

## Snippets

[链接](https://code.visualstudio.com/docs/editor/userdefinedsnippets)

### Variables

直接从官网复制的...
With `$name` or `${name:default}`, you can insert the value of a variable. When a variable isn't set, its **default** or the empty string is inserted. When a variable is unknown (that is, its name isn't defined) the name of the variable is inserted and it is transformed into a placeholder.

The following variables can be used:

- `TM_SELECTED_TEXT` The currently selected text or the empty string
- `TM_CURRENT_LINE` The contents of the current line
- `TM_CURRENT_WORD` The contents of the word under cursor or the empty string
- `TM_LINE_INDEX` The zero-index based line number
- `TM_LINE_NUMBER` The one-index based line number
- `TM_FILENAME` The filename of the current document
- `TM_FILENAME_BASE` The filename of the current document without its extensions
- `TM_DIRECTORY` The directory of the current document
- `TM_FILEPATH` The full file path of the current document
- `CLIPBOARD` The contents of your clipboard
- `WORKSPACE_NAME` The name of the opened workspace or folder
- `WORKSPACE_FOLDER` The path of the opened workspace or folder

For inserting the current date and time:

- `CURRENT_YEAR` The current year
- `CURRENT_YEAR_SHORT` The current year's last two digits
- `CURRENT_MONTH` The month as two digits (example '02')
- `CURRENT_MONTH_NAME` The full name of the month (example 'July')
- `CURRENT_MONTH_NAME_SHORT` The short name of the month (example 'Jul')
- `CURRENT_DATE` The day of the month
- `CURRENT_DAY_NAME` The name of day (example 'Monday')
- `CURRENT_DAY_NAME_SHORT` The short name of the day (example 'Mon')
- `CURRENT_HOUR` The current hour in 24-hour clock format
- `CURRENT_MINUTE` The current minute
- `CURRENT_SECOND` The current second
- `CURRENT_SECONDS_UNIX` The number of seconds since the Unix epoch

For inserting line or block comments, honoring the current language:

- `BLOCK_COMMENT_START` Example output: in PHP /* or in HTML <!--
- `BLOCK_COMMENT_END` Example output: in PHP */ or in HTML -->
- `LINE_COMMENT` Example output: in PHP //

The snippet below inserts `/* Hello World */` in JavaScript files and `<!-- Hello World -->` in HTML files:

```json
{
  "hello": {
    "scope": "javascript,html",
    "prefix": "hello",
    "body": "$BLOCK_COMMENT_START Hello World $BLOCK_COMMENT_END"
  }
}
```

### Assign keybindings to snippets

You can create custom keybindings to insert specific snippets. Open keybindings.json (Preferences: Open Keyboard Shortcuts File), which defines all your keybindings, and add a keybinding passing "snippet" as an extra argument:

```json
{
  "key": "cmd+k 1",
  "command": "editor.action.insertSnippet",
  "when": "editorTextFocus",
  "args": {
    "snippet": "console.log($1)$0"
  }
}
```

The keybinding will invoke the Insert Snippet command but instead of prompting you to select a snippet, it will insert the provided snippet. You define the custom keybinding as usual with a keyboard shortcut, command ID, and optional when clause context for when the keyboard shortcut is enabled.

Also, instead of using the snippet argument value to define your snippet inline, you can reference an existing snippet by using the langId and name arguments. The langId argument is the name of the JSON user snippet file and name is the snippet's unique name from this file:

```json
{
  "key": "cmd+k 1",
  "command": "editor.action.insertSnippet",
  "when": "editorTextFocus",
  "args": {
    "langId": "csharp",
    "name": "myFavSnippet"
  }
}
```

## Key Bindings

[链接](https://code.visualstudio.com/docs/getstarted/keybindings)

## plunges

- Markdown All In One

> 搭配 [pandoc](https://www.pandoc.org/) 使用更佳

- Polacode

> 生成漂亮的代码块图片

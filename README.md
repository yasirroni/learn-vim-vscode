# Learn Vim VSCode

My journey to learn Vim is written here. Everything here I write under the VSCode Vim extension.

## Extensions

1. [vscodevim.vim](https://marketplace.visualstudio.com/items?itemName=vscodevim.vim)

2. [vintharas.learn-vim](https://marketplace.visualstudio.com/items?itemName=vintharas.learn-vim)

## Notes for beginner

1. Disable `ctrl`

    For my first time learning Vim, I disable `vim.useCtrlKeys`. In `.vscode/settings.json`,

    ```json
    {
        "vim.useCtrlKeys": false
    }
    ```

    This will allow me to use `ctrl+c` and `ctrl+v` as copy and paste respectively. The downside is, all Vim commands that use `ctrl` will not work as expected.

1. Disable accepting suggestion using `enter`

    This setting is because `enter` is used to change lines in Python. To accept auto-complete, `tab`` can still be used.

    ```json
    {
        "editor.acceptSuggestionOnEnter": "off",
    }
    ```

1. TODO: support left and right arrows to support change lines to the last or first line of another line. But, this option can create a bad habit of not using Vim command mode.

1. Use `a` instead of `i`

    Instead of using `i` to enter insert mode, using `a` is better for beginners because `a` will place the cursor after the location of the selected character, whereas `i` place it before the character. See [this](https://stackoverflow.com/questions/41657784/inserting-at-the-end-of-a-line-in-vim) Stack Overflow question for more details and motives. But, mastering both keys are better.

1. Support change line using arrow key in warped text inside insert mode

    1. Open vscode's shortcut setting using `ctrl+k+s`.
    1. In the search bar (In my case, it brings UI with a search bar), enter `cursorUp`.
    1. Right click on `cursorUp` row, and select the `Change` When Expression`.
    1. Change to `editorTextFocus && vim.active && !inDebugRepl && vim.mode == 'Insert' && !suggestWidgetMultipleSuggestions && !suggestWidgetVisible`.
    1. In the search bar (In my case, it brings UI with a search bar), enter `cursorDown`.
    1. Right click on `cursorDown` row, and select the `Change` When Expression`.
    1. Change to `editorTextFocus && vim.active && !inDebugRepl && vim.mode == 'Insert' && !suggestWidgetMultipleSuggestions && !suggestWidgetVisible`.

    For more information, see [here](https://github.com/VSCodeVim/Vim/issues/2924#issuecomment-1238252236).

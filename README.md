# Learn Vim VSCode

My journey to learn Vim is written here. Everyhthing here I write under VSCode Vim extension.

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

1. Use `a` instead of `i`

    Instead of using `i` to enter insert mode, use `a` is better for beginner because `a` will place the cursor after the location of the selected characted, whereas `i` place it before the caracter. See [this](https://stackoverflow.com/questions/41657784/inserting-at-the-end-of-a-line-in-vim) Stack Overflow question for more details and motives. But, master both keys are better.

1. Support change line using arrow key in warped text inside insert mode

    1. Open vscode's shortcut setting using `ctrl+k+s`.
    1. In the search bar (In my case, it brings UI with search bar), enter `cursorUp`.
    1. Righ click on `cursorUp` row, select the `Change When Expression`.
    1. Change to `editorTextFocus && vim.active && !inDebugRepl && vim.mode == 'Insert' && !suggestWidgetMultipleSuggestions && !suggestWidgetVisible`.
    1. In the search bar (In my case, it brings UI with search bar), enter `cursorDown`.
    1. Righ click on `cursorDown` row, select the `Change When Expression`.
    1. Change to `editorTextFocus && vim.active && !inDebugRepl && vim.mode == 'Insert' && !suggestWidgetMultipleSuggestions && !suggestWidgetVisible`.

    For more information, see [here](https://github.com/VSCodeVim/Vim/issues/2924#issuecomment-1238252236).

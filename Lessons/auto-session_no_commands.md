# Overview

After installing the neovim plugin `auto-session`, I was not able to use any of the editor commands, such as `:SessionSave` or `:SessionRestore`.

This was despite setting `lazy = false` (using NvChad, `lazy = true` by default).

# Solution

Manually setting the config in the plugin file to:

```lua
config = function()
    require("auto-session").setup {
        auto_session_root_dir = vim.fn.stdpath "data" .. "/sessions/",
    }
end,
```

resolved this for me.

# Credit

Credit to https://github.com/rmagatti/auto-session/issues/271 for the solution.

# Tags

- neovim
- auto-session
- nvchad
- lunarvim
- command not found

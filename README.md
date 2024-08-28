# Sourcepawn support for the Zed Editor

This extension adds basic language support, highlighting & LSP, to the Zed Editor for Sourcepawn.

Keep in mind that currently themes use a fairly restricted number of captures, so unfortunately it'll look fairly bland and "less colorful" compared to VSCode or Neovim.
You could make a theme ad hoc for Sourcepawn that properly supports all of the captures, but of course it'd work only on that specific theme.

## Customization

You'll want to provide some additional information for the LSP such as your include path & compiler path.

To do so, press `ctrl + shift + p` and type `zed: open settings`. Once there, you're free to change whatever you want about the LSP.
To provide an example, here is how you'd add an include and compiler paths:
```json
{
  "features": {
    "inline_completion_provider": "none"
  },
  "ui_font_size": 16,
  "buffer_font_size": 16,
  "theme": {
    "mode": "system",
    "light": "One Light",
    "dark": "One Dark"
  },
  // Add the following entries unless they already exist.
  "lsp": {
    "sourcepawn-studio": {
      "initialization_options": {
        // Whatever settings you want:
        "includeDirectories": ["/mnt/suzanas/Coding/SourcePawn/Scripts/Include"],
        "compiler": {
          "path": "/home/suza/Compiled/spcomp"
        },
      }
    }
  }
}
```

For a more thorough list of settings and their meanings, check it out [here](https://sarrus1.github.io/sourcepawn-studio/docs/configuration/lsp-settings-reference).

## Credits
All of the credits go to the developers of the LSP & grammar of Sourcepawn:
- LSP: https://github.com/Sarrus1/sourcepawn-studio
- Grammar: https://github.com/nilshelmig/tree-sitter-sourcepawn

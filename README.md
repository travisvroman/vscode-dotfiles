# vscode-dotfiles

My user-level VSCode dotfiles, because people asked for it.

These files are organized in such a way where you can simply drop them into your .config folder OR, the approach I would recommend is to symlink these files instead.

## Clone

Navigate to a directory in the terminal. I suggest using your home directory:
Just `cd` (no path) for macOS/Linux or `cd %USERPROFILE%` for Windows.

Clone the repo to that directory:
`git clone git@github.com:travisvroman/vscode-dotfiles.git`

## How Symlink

This assumes you've cloned this repo in your home directory, otherwise you will need to modify the source path.

### Linux

- Make sure target folder exists: `mkdir -p ~/.config/Code/User/`
- Ensure settings.json does not already exist: `mv ~/.config/Code/User/settings.json ~/.config/Code/User/settings.original.json`
- Ensure keybindings.json does not already exist: `mv ~/.config/Code/User/keybindings.json ~/.config/Code/User/keybindings.original.json`
- Symlink settings.json: `ln -s ~/vscode-dotfiles/.config/User/Code/settings.json ~/.config/User/Code/settings.json`
- Symlink keybindings.json: `ln -s ~/vscode-dotfiles/.config/User/Code/keybindings.json ~/.config/User/Code/keybindings.json`

### macOS

- Make sure target folder exists: `mkdir -p ~/.config/Code/User/`
- Ensure settings.json does not already exist: `mv ~/Library/Application\ Support/Code/User/settings.json ~/Library/Application\ Support/Code/User/settings.original.json`
- Ensure keybindings.json does not already exist: `mv ~/Library/Application\ Support/Code/User/keybindings.json ~/Library/Application\ Support/Code/User/keybindings.original.json`
- Symlink settings.json: `ln -s ~/vscode-dotfiles/.config/User/Code/settings.json ~/Library/Application\ Support/Code/User/settings.json`
- Symlink keybindings.json: `ln -s ~/vscode-dotfiles/.config/User/Code/keybindings.json ~/Library/Application\ Support/Code/User/keybindings.json`

### Windows

- Make sure target folder exists: `if not exists %APPDATA%\Code\User\ mkdir %APPDATA%\Code\User\`
- Ensure settings.json does not already exist: `mv %APPDATA%\Code\User\settings.json %APPDATA%\Code\User\settings.original.json`
- Ensure keybindings.json does not already exist: `mv %APPDATA%\Code\User\keybindings.json %APPDATA%\Code\User\keybindings.original.json`
- Symlink settings.json: `mklink /D %APPDATA%\Code\User\settings.json %USERPROFILE%\vscode-dotfiles\.config\User\Code\settings.json`
- Symlink keybindings.json: `mklink /D %APPDATA%\Code\User\keybindings.json %USERPROFILE%\vscode-dotfiles\.config\User\Code\keybindings.json`

See this page for more details if needed:
https://code.visualstudio.com/docs/getstarted/settings

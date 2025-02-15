# Tmux Configuration

A production-grade tmux configuration with enhanced workflow features, vim-style navigation, and aesthetic improvements. Designed for developers who work in terminal multiplexing environments.

## Features

- **Key Bindings**

  - Prefix key: `Ctrl+a` (more ergonomic than default `Ctrl+b`)
  - Vim-style pane navigation (`h/j/k/l`)
  - Seamless Vim/tmux navigation integration
  - Pane resizing with modifier keys
  - Window management shortcuts

- **Visual Enhancements**

  - Catppuccin theme integration
  - 256-color support
  - Customizable status bar with date/time
  - Top-aligned status bar position

- **Workflow Improvements**
  - TPM plugin management
  - Yank integration for system clipboard
  - Mouse support with scroll compatibility
  - Session persistence for panes/windows
  - Automatic TPM installation
  - Synchronized panes toggle

## Installation

1. Clone repository:

```bash
git clone https://github.com/Mohabdo21/tmux-config.git ~/.tmux
```

2. Create symlink:

```bash
ln -s ~/.tmux/.tmux.conf ~/.tmux.conf
```

3. Install TPM (if not auto-installed):

```bash
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

4. Start tmux and load config:

```bash
tmux source-file ~/.tmux.conf
```

## Configuration

Customize these values in `.tmux.conf`:

```tmux
# Change theme
set -g @plugin 'your-theme/tmux-theme'

# Modify datetime format
set -g @catppuccin_date_time "%Y-%m-%d %H:%M:%S"

# Adjust base indices
set -g base-index 1              # Start window numbering at 1
setw -g pane-base-index 1        # Start pane numbering at 1
```

## Plugin Management

Included plugins:

- [TPM](https://github.com/tmux-plugins/tpm) - Tmux Plugin Manager
- [tmux-sensible](https://github.com/tmux-plugins/tmux-sensible) - Default settings
- [Catppuccin Theme](https://github.com/catppuccin/tmux) - Color scheme
- [tmux-yank](https://github.com/tmux-plugins/tmux-yank) - Clipboard integration

Add new plugins:

1. Add to plugin list:

```tmux
set -g @plugin 'author/plugin-name'
```

2. Press `Prefix + I` to install

## Key Bindings

| Command                   | Action                      |
| ------------------------- | --------------------------- |
| `Ctrl+a`                  | Enter command mode          |
| `Prefix + h/j/k/l`        | Navigate panes              |
| `Prefix + H/J/K/L`        | Resize panes                |
| `Prefix + C-x`            | Zoom active pane            |
| `Prefix + z`              | Toggle pane synchronization |
| `Prefix + C-S-Left/Right` | Move window position        |

## Troubleshooting

**Terminal Colors Not Working:**

1. Verify terminal emulator supports 256 colors
2. Ensure `$TERM` is set to `xterm-256color`
3. Confirm terminal-overrides in config:

```tmux
set -sa terminal-overrides ',xterm-256color:Tc'
```

**Plugin Issues:**

1. Clean TPM install:

```bash
rm -rf ~/.tmux/plugins/
```

2. Reinstall plugins with `Prefix + I`

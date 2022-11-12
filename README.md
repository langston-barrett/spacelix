# Spacelix

Spacelix is [Spacemacs][spacemacs] for [Helix][helix]! This project consists of
two Helix configurations:

- [spacemacs-compat.toml](./src/spacemacs-compat.toml) ports Spacemacs
  keybindings to Helix. It's useful for Spacemacs users who would like to try
  Helix and gradually learn new keybindings, rather than all at once.
- [spacelix.toml](./src/spacelix.toml) is a Helix configuration built with
  Spacemacs-style principles in mind, but it does not strive to emulate
  Spacemacs. It often has shorter key sequences than `spacemacs-compat.toml`.

The remainder of this README discusses `spacelix.toml`, AKA Spacelix.

The Spacelix keybindings are designed according to the following goals:

- [Mnemonic][pillar-mnemonic]: Key bindings are organized using mnemonic
  prefixes like b for buffer, w for window, f for file, etc…
- [Consistent][pillar-consistent]: Similar functionalities have the same key
  binding everywhere thanks to a clearly defined set of conventions.
- Safe: Spacelix avoids modifier keys (shift, ctrl) to reduce the risk of RSI.

## Bindings

Some of these bindings match Helix defaults, those are marked with "(default)".

<!-- - `SPC b w`: TODO buffer write? -->

- `SPC`
  - `SPC SPC`: Command palette
  - `SPC a`: Code action (default)
  - `SPC b`: Buffers
    - `SPC b b`: Buffer picker
    - `SPC b d`: Close buffer (mnemonic: "delete")
    - `SPC b D`: Force close buffer (`:buffer-close!`)
    - `SPC b n`: Next buffer
    - `SPC b p`: Previous buffer
    - `SPC b r`: Reload buffer (`:reload`)
    - `SPC b s`: Scratch buffer (`:new`)
    - `SPC b y`: Yank buffer (`select_all`, `yank`)
    - `SPC b Y`: Yank buffer to system clipboard (`select_all`,
      `:clipboard-yank`)
  - `SPC c`: Case (select mode only)
    - `SPC c c`: Toggle case
    - `SPC c u`: Uppercase
    - `SPC c l`: Lowercase
  - `SPC d`: Debug (default)
  - `SPC e`: Errors
    - `SPC e g`: Go to first error
    - `SPC e G`: Go to last error
    - `SPC e l`: List errors (diagnostic picker)
    - `SPC e n`: Go to next error
    - `SPC e p`: Go to previous error
  - `SPC f`: File picker
  - `SPC o`: Reserved for user mappings
  - `SPC q`: Quit
    - `SPC q a`: Quit all (`:quit-all`)
    - `SPC q A`: Force quit all (`:quit-all!`)
    - `SPC q c`: Quit with exit code (`:cquit`)
    - `SPC q C`: Force quit with exit code (`:cquit!`)
    - `SPC q q`: Quit (`:quit`)
    - `SPC q Q`: Force quit (`:quit!`)
    - `SPC q w`: Write and quit (`:write-quit`)
    - `SPC q W`: Force write and quit (`:write-quit!`)
  - `SPC g`: Go to
    - `SPC g f`: Go to file
      - `SPC g f a`: Go to last accessed file
      - `SPC g f f`: Go to files in selection
      - `SPC g f m`: Go to last modified file
      - `SPC g f h`: Go to files in selection (horizontal split)
      - `SPC g f v`: Go to files in selection (vertical split)
    - `SPC g d`: Go to definition
    - `SPC g g`: Go to first line of file
    - `SPC g G`: Go to last line of file
    - `SPC g h`: Go to start of line
    - `SPC g i`: Go to implementation
    - `SPC g l`: Go to end of line
    - `SPC g m`: Go to last modification
    - `SPC g t`: Go to top of window
    - `SPC g b`: Go to bottom of window
    - `SPC g c`: Go to center of window
    - `SPC g r`: Go to references
    - `SPC g s`: Go to symbol definition (symbol picker)
    - `SPC g w`: Go to first non-whitespace character in line
    - `SPC g y`: Go to type definition
  - `SPC h`: Global search
  - `SPC j`: Jumplist
    - `SPC j j`: Open the jumplist picker
    - `SPC j n`: Jump forward in the jumplist (mnemonic: "next")
    - `SPC j p`: Jump backward in the jumplist (mnemonic: "previous")
    - `SPC j s`: Save current selection in the jumplist
  - `SPC s`: Save (`:write`)
  - `SPC r`: Rename symbol (default)
  - `SPC w`: Windows
    - `SPC w d`: Close window (mnemonic: "delete")
    - `SPC w h`: Go to window (left) (default)
    - `SPC w j`: Go to window (down) (default)
    - `SPC w k`: Go to window (up) (default)
    - `SPC w l`: Go to window (right) (default)
    - `SPC w o`: Close windows other than current (default)
    - `SPC w H`: Swap window (left) (default)
    - `SPC w J`: Swap window (down) (default)
    - `SPC w K`: Swap window (up) (default)
    - `SPC w L`: Swap window (right) (default)
  - `SPC X`: Helix
    - `SPC X f`: Open configuration file
    - `SPC X l`: Open the Helix log file
    - `SPC X r`: Reload configuration
    - `SPC X t`: Tutor

The following key bindings are for `vi`/Spacemacs-emulation purposes.

- Normal mode:
  - `0`: Go to start of line
  - `$`: Go to end of line
  - `H`: Go to top of window
  - `L`: Go to bottom of window
  - `M`: Go to center of window
- Select mode:
  - `0`: Go to start of line
  - `$`: Go to end of line
  - `H`: Select previous sibling

And the following are just for good measure:

- Select mode:
  - `J`: Shrink selection
  - `K`: Expand selection
  - `L`: Select next sibling
  - `M`: Go to center of window

## Conventions and Mnemonics

- `n` means "next", preferred over "forward"
- `p` means "previous", preferred over "backward"

[helix]: https://helix-editor.com/
[pillars]: https://www.spacemacs.org/doc/DOCUMENTATION.html#core-pillars
[pillar-mnemonic]: https://www.spacemacs.org/doc/DOCUMENTATION.html#mnemonic
[pillar-consistent]: https://www.spacemacs.org/doc/DOCUMENTATION.html#consistent
[spacemacs]: https://www.spacemacs.org/

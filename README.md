# Zellij Launcher (ZL)

A customizable launcher for [Zellij](https://github.com/zellij-org/zellij) inspired by [ThePrimeagen's tmux sessionizer](https://github.com/ThePrimeagen/.dotfiles/blob/master/bin/.local/scripts/tmux-sessionizer) and [alex35mil's zellij-runner](https://github.com/alex35mil/dotfiles/tree/master/user/bin/zellij/runner).

## Dependencies

- [Zellij](https://github.com/zellij-org/zellij) (duh)
- [fzf](https://github.com/junegunn/fzf)

## Installation and Usage

Download the file `zellij-launcher` or paste its contents into your own file:

```bash
curl https://raw.githubusercontent.com/ChuseCubr/zellij-launcher/master/zellij-launcher -o ~/.config/zellij/zellij-launcher
```

Source that file in your `~/.bashrc`:

```bash
# ... your other stuff here
source ~/.config/zellij/zellij-launcher
```

## Settings and Customization

The default options are meant to showcase all the features of the script, so it's pretty crowded by default.

The script can be customized by setting environment variables:

```bash
# Space separated list of the different main menu options.
# This default includes all options.
ZELLIJ_LAUNCHER_MENU="create attach kill reload exit sessions locations"

# If your menu includes actions (create, kill, reload, exit),
# they will be prepended with this string for clarity.
ZELLIJ_LAUNCHER_ACTION_PREFIX="$ "

# Space separated string of directories to search when creating a new session.
# Use $HOME instead of ~ and \$PWD instead of $PWD.
ZELLIJ_LAUNCHER_DIRS="\$PWD $HOME"

# Minimum search depth (find -mindepth)
ZELLIJ_LAUNCHER_MIN_DIR_DEPTH=0

# Maximum search depth (find -maxdepth)
ZELLIJ_LAUNCHER_MAX_DIR_DEPTH=3

# Opts to pass to fzf in case you don't like this layout
ZELLIJ_LAUNCHER_FZF_OPTS="--layout=reverse --inline-info --border --header-first --cycle"

# Let the user start a session even if already attached to one.
# Be careful, you can break sessions if you recurse them!
# For example: (main session > split > new session > attach to main session)
ZELLIJ_LAUNCHER_ALLOW_NEST=1

# If you open the launcher within an active Zellij session,
# display the current session in the header/banner.
# Only applies when ZELLIJ_LAUNCHER_ALLOW_NEST is enabled
ZELLIJ_LAUNCHER_SHOW_CURRENT=1

# When enabled, detaching from a session and not selecting anything
# in the main menu will return you to your last attached session.
# Enabling this option forcibly adds exit to the main menu.
ZELLIJ_LAUNCHER_RETURN_TO_LAST=1

# When enabled, only show the exit action in the main menu when there are no
# recent sessions.
# This setting only takes effect when ZELLIJ_LAUNCHER_RETURN_TO_LAST
# is enabled.
ZELLIJ_LAUNCHER_DYNAMIC_EXIT=1

# Applied when selecting a folder in the main menu whose name is already an
# active sessions.
# If nested and the selected folder name is the attached session,
# will automatically be set to rename.
# Possible values: "attach" | "rename" | "ask"
ZELLIJ_LAUNCHER_FOLDER_BEHAVIOR="ask"

# Text always displayed in menus.
# I recommend keeping this so Zellij gets exposure :)
ZELLIJ_LAUNCHER_BANNER=" 
███████╗███████╗██╗     ██╗     ██╗     ██╗
╚══███╔╝██╔════╝██║     ██║     ██║     ██║
  ███╔╝ █████╗  ██║     ██║     ██║     ██║
 ███╔╝  ██╔══╝  ██║     ██║     ██║██   ██║
███████╗███████╗███████╗███████╗██║╚█████╔╝
╚══════╝╚══════╝╚══════╝╚══════╝╚═╝ ╚════╝ 
 "
```

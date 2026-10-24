# devfetch

A neofetch-style spec screen for Chromebooks running Linux (Crostini), made for
photographing a laptop for a marketplace listing.

CPU, RAM, OS, kernel and installed dev tools are detected live. Things Crostini
can't see, such as the real model name, SSD size and display, come from a
config file you can change from the command line.

## Install

```sh
git clone https://github.com/Regular-2000/devfetch.git ~/projects/devfetch
mkdir -p ~/.local/bin
ln -sf ~/projects/devfetch/devfetch ~/.local/bin/devfetch
devfetch
```

## Usage

```sh
devfetch                                   # show the screen
devfetch --set storage "256 GB NVMe SSD"   # set or override a field
devfetch --set battery "Holds a full day"  # any new key adds a custom line
devfetch --unset battery                   # remove it / go back to auto-detect
devfetch --set accent 208                  # label colour (256-colour number)
devfetch --set header "dev@latitude"       # replace user@host
devfetch --config                          # print the config
devfetch --edit                            # open the config in $EDITOR
```

Config lives in `~/.config/devfetch/config` as plain `KEY=value` lines.

Built-in fields: `MODEL`, `CPU`, `RAM`, `STORAGE`, `DISPLAY`, `OS`, `KERNEL`,
`TOOLS`. Settings: `HEADER`, `TAGLINE`, `ACCENT`.

## Photo tips

Press **Ctrl +** in the Terminal to enlarge the text, then run `clear; devfetch`.

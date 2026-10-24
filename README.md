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
devfetch --set big "32GB|i3"               # custom headline; "|" splits colour segments
devfetch --set colors "81 214"             # one 256-colour number per segment
devfetch --set colors2 "31 172"            # colour of the trailing word (RAM, SSD)
devfetch --set big off                     # hide the headline
devfetch --set font big                    # figlet font (ls /usr/share/figlet)
devfetch --config                          # print the config
devfetch --edit                            # open the config in $EDITOR
```

Config lives in `~/.config/devfetch/config` as plain `KEY=value` lines.

Built-in fields: `MODEL`, `CPU`, `RAM`, `STORAGE`, `DISPLAY`, `OS`, `KERNEL`,
`TOOLS`. Settings: `HEADER`, `TAGLINE`, `ACCENT`, `BIG`, `FONT`, `COLORS`, `COLORS2`.

If `figlet` is installed (`sudo apt install figlet`), a large headline built
from RAM and storage (`32 GB RAM` and `128 GB SSD`, each in its own colour; "RAM"
is spelled out so nobody mistakes it for eMMC size) is printed
above the screen in solid block letters. Segments sit side by side when the
terminal is wide enough and stack otherwise.

## Photo tips

Press **Ctrl +** in the Terminal to enlarge the text, then run `clear; devfetch`.

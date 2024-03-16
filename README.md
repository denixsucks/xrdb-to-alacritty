# Xresources to Alacritty

Regex based solution to export Xresources colors into Alacritty config with one command.

Tested on Artix Linux with Alacritty (0.13.1) and works as intended.
Sed commands may differ on untested distros and give errors.

## Installation
**Deps:** grep, sed, xrdb

You can simply go to [raw file](https://github.com/denixsucks/xrdb-to-alacritty/raw/master/script.sh) and save the file to your script directory or open your terminal emulator:

```sh
git clone https://github.com/denixsucks/xrdb-to-alacritty
cd xrdb-to-alacritty
chmod +x script.sh
```

## Usage
```sh
# Execute
./script.sh

# Execute with custom config
./script.sh <config.toml>
```

## Example

##### Terminal emulator:

```bash
$ ./script.sh
```

##### Input (~/.Xresources):

```
...
*background: #303446
*foreground: #C6D0F5

! black
*color0: #51576D
*color8: #626880

! red
*color1: #E78284
*color9: #E78284

! green
*color2: #A6D189
*color10: #A6D189

! yellow
*color3: #E5C890
*color11: #E5C890

! blue
*color4: #8CAAEE
*color12: #8CAAEE

! magenta
*color5: #F4B8E4
*color13: #F4B8E4

! cyan
*color6: #81C8BE
*color14: #81C8BE

! white
*color7: #B5BFE2
*color15: #A5ADCE
...

```

##### Output (~/.config/alacritty/alacritty.toml):

```toml
...
# BEGIN XTA
[colors.primary]
background = "#303446"
foreground = "#C6D0F5"

[colors.normal]
black = "#51576D"
red = "#E78284"
green = "#A6D189"
yellow = "#E5C890"
blue = "#8CAAEE"
magenta = "#F4B8E4"
cyan = "#81C8BE"
white = "#B5BFE2"

[colors.bright]
black = "#626880"
red = "#E78284"
green = "#A6D189"
yellow = "#E5C890"
blue = "#8CAAEE"
magenta = "#F4B8E4"
cyan = "#81C8BE"
white = "#A5ADCE"
# END XTA
...
```

## Potential Issues
- ~~If there isn't ``# BEGIN XTA`` comment, the script wipes out whole config.~~

## Contribution
Don't forget to backup config and thank you for your contribution in advance. Any information from testing on different systems would valuable to anyone who interested in this script. Issues and PR's are welcomed.

## License
This software is under [The Do What The Fuck You Want To Public License (WTFPL)](http://www.wtfpl.net/about/).

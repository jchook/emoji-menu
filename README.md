# 🎩 Emoji Menu

Easily find and copy emojis on Linux. 🥳


![Demo](https://d3vv6lp55qjaqc.cloudfront.net/items/3F2e2K433s0T301d0Z0n/Peek%202019-01-04%2019-05%20take%205.gif?X-CloudApp-Visitor-Id=152352&v=a32b86c6)


## ✨ Install

Simply install `emoji-menu` to your `$PATH`:

```sh
wget 'https://bit.ly/emoji-menu'
chmod +x emoji-menu
sudo mv emoji-menu /usr/local/bin
```

Be sure to install the dependencies as well

```sh
# For non-Debian, replace apt with your package manager (e.g. yum)
sudo apt install rofi xclip xdotool wget grep coreutils
```

* `rofi` works like dmenu, but supports large input.
* `xclip` lets us copy to clipboard.
* `xdotool` lets us type the result.
* You already have `wget`, `grep`, and `coreutils`.


## 👨‍🎤 Emojis

By default the program automatically downloads *all emojis* on first run.

The `$EMOJI_MENU_DB` environment variable defaults to `~/.emoji-menu-db`.

To customize, store one emoji per line with its keywords, e.g.

```
✨ sparkles stars magic
🧙 mage wizard magician
🌍 globe earth europe africa
```

Pretty simple! You can add other strings too. They don't have to be emojis.

## 🧙 Options

When invoking `emoji-menu`, you may pass the following options:

* `-f <filename>` - Use a custom emoji database
* `-c <command>` - Run a custom command on emoji choices
* `-t` - Simulate typing the emoji choice using the keyboard


## *️⃣ Hotkeys

You definitely want `emoji-menu` on a [hotkey](https://wiki.archlinux.org/index.php/Keyboard_shortcuts#Customization).

In the examples below, I assign <kbd>Mod</kbd> + <kbd>Ctrl</kbd> + <kbd>x</kbd>.

#### Generic

For a solution that works on most window managers, try [xbindkeys](https://wiki.archlinux.org/index.php/Xbindkeys). In your config:

```sh
"emoji-menu"
  control+alt + x
```

#### Xmonad

If you use Xmonad as your window manager, set [keys](http://hackage.haskell.org/package/xmonad-0.15/docs/XMonad-Core.html#t:XConfig) [config](https://github.com/vicfryzel/xmonad-config/blob/85c2ca392125ade3bb122e72a99af640896a0727/xmonad.hs#L160-L162) like so:

```haskell
  -- Emoji Menu
 , ((modMask .|. controlMask, xK_x),
    spawn "emoji-menu")
```

#### i3wm

For i3 add a [bindsym](https://i3wm.org/docs/userguide.html#keybindings) to your [config](https://i3wm.org/docs/userguide.html#configuring):

```sh
bindsym $mod+Control+x emoji-menu
```

#### Other

If none of the above works for you, please open an [issue](https://github.com/jchook/emoji-menu/issues/new).

## ❤️ Thank you

Thank you for checking out `emoji-menu`. I enjoy using it and hope you do too.

## 📖 License

Copyright 2019 Zinc Innovations, LLC.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

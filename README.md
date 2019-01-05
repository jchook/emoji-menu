# 🧭 Emoji Menu

🔍 Easily find and copy emojis on Linux. 😀


![](https://d3vv6lp55qjaqc.cloudfront.net/items/3F2e2K433s0T301d0Z0n/Peek%202019-01-04%2019-05%20take%205.gif?X-CloudApp-Visitor-Id=152352&v=a32b86c6)



## Depdencies

How else could this fit into one line of bash?

```sh
# For non-Debian, replace apt with your package manager
sudo apt install xclip rofi
```

* `xclip` lets us copy to clipboard.
* `rofi` works like dmenu, but supports large input.

## Emojis

First, you decide which emojis and keywords you want via a simple text file. E.g.

```
✨ sparkles stars magic
🧙 mage wizard magician
🌍 globe earth europe africa
```

To start with **all emojis** try this:

```sh
curl -s 'https://unicode.org/Public/emoji/11.0/emoji-test.txt' \
  | grep -oP '(?<=   #).*' \
  > ~/.emoji-menu-db
```

The `$EMOJI_MENU_DB` environment variable defaults to `~/.emoji-menu-db`.


## Install

Once you have your emojis, install [`emoji-menu`](https://github.com/jchook/emoji-menu/blob/master/bin/emoji-menu) to your `$PATH`.

```sh
wget 'https://bit.ly/emoji-menu'
chmod +x emoji-menu
sudo mv emoji-menu /usr/local/bin
```

Alternatively you could clone the git repository and add its `bin` folder to your `$PATH`.


## Hotkeys

You definitely want this bad boy on a [hotkey](https://wiki.archlinux.org/index.php/Keyboard_shortcuts#Customization), e.g. <kbd>Mod</kbd> + <kbd>Ctrl</kbd> + <kbd>x</kbd>.

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

#### i3

For i3 add a [bindsym](https://i3wm.org/docs/userguide.html#keybindings) to your [config](https://i3wm.org/docs/userguide.html#configuring):

```sh
bindsym $mod+Control+x emoji-menu
```

## License

Copyright 2019 Zinc Innovations, LLC.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

# 🧭 Emoji Menu

🔍 Easily find and copy emojis on Linux. 😀


![](https://d3vv6lp55qjaqc.cloudfront.net/items/3F2e2K433s0T301d0Z0n/Peek%202019-01-04%2019-05%20take%205.gif?X-CloudApp-Visitor-Id=152352&v=a32b86c6)



## Depdencies

How else could this fit into one line of bash?

```sh
sudo apt install xclip rofi
```

> `xclip` lets us copy to clipboard, and `rofi` works like dmenu, but supports emojis and huge input.

## Emojis

First, you decide which emojis and keywords you want via a simple text file. E.g.

```
❤️ heart symbol red
😎 cool face sunglasses
🌍 globe earth europe africa
```

If you want to start with **all emojis** try this:

```sh
mkdir -p ~/.config/emoji-menu

curl 'https://unicode.org/Public/emoji/11.0/emoji-test.txt' \
  | grep -oP '(?<=   #).*' \
  > ~/.config/emoji-menu/emojis.txt
```

> `emoji-menu` looks for your emojis file at `$EMOJIS_FILE`, which defaults to `~/.config/emoji-menu/emojis.txt`.


## Install

Once you have your `emojis.txt`, just copy `bin/emoji-menu` to your `$PATH`.

```sh
# Download emoji-menu
sudo curl \
  -o /usr/local/bin/emoji-menu \
  -s https://raw.githubusercontent.com/jchook/emoji-menu/master/bin/emoji-menu

# Make it executeable
sudo chmod +x /usr/local/bin/emoji-menu
```

> Alternatively you could clone the git repository and add its `bin` to your `$PATH`.


## License

MIT.

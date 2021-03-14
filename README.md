# 🎩 Emoji Menu

Easily find and copy emojis on Linux. 🥳

![Demo](https://d3vv6lp55qjaqc.cloudfront.net/items/3F2e2K433s0T301d0Z0n/Peek%202019-01-04%2019-05%20take%205.gif?X-CloudApp-Visitor-Id=152352&v=a32b86c6)
  

## whats the difference with the upstream

This is modified to have only one option:  to paste the selected option AND copy it to clipboard.  
You can also have phrases instead of just words or emojis by separating the words with underscore.  
  
Make sure to check the [original project](https://github.com/jchook/emoji-menu) to see if it suits you better.

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

- `rofi` works like dmenu, but supports large input.
- `xclip` lets us copy to clipboard.
- `xdotool` lets us type the result.
- You already have `wget`, `grep`, and `coreutils`.

## 👨‍🎤 Emojis

By default the program automatically downloads _all emojis_ on first run.

The `$EMOJI_MENU_DB` environment variable defaults to `~/.emoji-menu-db`.

To customize, store one emoji per line with its keywords, e.g.

```
✨ sparkles stars magic
🧙 mage wizard magician
🌍 globe earth europe africa
good_mornings_🌇 gm
```

Pretty simple! You can add other strings too. They don't have to be emojis.

## \*️⃣ Hotkeys

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

#### Elementary OS

Simply add a custom shortcut by navigating to `Settings -> Shortcuts -> Custom`  
add the command `emoji-menu` and the shortcut of your choice  
  
#### Other

If none of the above works for you, please open an [issue](https://github.com/jchook/emoji-menu/issues/new).

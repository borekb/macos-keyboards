# My macOS keyboard layouts

Customized keyboard layouts created with [Ukelele](https://scripts.sil.org/ukelele).

## How to install

1. Copy the keyboard layout:
    ```
    sudo cp -r Xyz.bundle /Library/Keyboard\ Layouts
    ```
    (Don't use the built-int organizer in Ukelele as it [removes the bundle from the original location](https://groups.google.com/forum/#!topic/ukelele-users/90YkwlJoCIg).)
2. Log out & back in, or remove the keyboard layout from Input Sources and add it back in.
3. Select keyboard in Input Sources.

## How to make customizations

Get [Ukelele](https://scripts.sil.org/ukelele): `brew cask install ukelele`. Then:

1. Open an existing bundle or create a new one via **File** > **New From Current Input Source**.
2. Double-click the keyboard layout.
3. On the virtual keyboard, double-click a key you want to remap and enter a character.
4. Give it a name via **Set Keyboard Name and Script...** (this is a different thing than a filename!)
5. [Install](#how-to-install) the keyboard and test it.
6. Update this README – screenshots and [changelog](#changelog).

## 'English BB' customizations

- Moves <code>&#96;</code> (backtick) to the top left corner. The overwritten `§` symbol can be written with Alt.
- Moves `\` and `|` to the key next to the left Shift (where backtick originally was).
    - `\` and `|` are still at their original location next to Enter.
    - **UPDATE Sep 2019**: This is problematic as e.g. [VSCode doesn't see `Cmd-\`](https://github.com/microsoft/vscode/issues/80697). See [Ukelele support thread](https://groups.google.com/forum/#!topic/ukelele-users/28lJPjzbpTQ).

| | U.S. | English BB |
| -- | -- | -- |
| | <img alt="U.S. basic" src="https://user-images.githubusercontent.com/101152/65379219-e7abaf80-dcc4-11e9-9d70-25d8fbc198b0.png"> | <img alt="English BB basic" src="https://user-images.githubusercontent.com/101152/65379184-563c3d80-dcc4-11e9-81f9-386aae2774ce.png"> |
| ⌥ | <img alt="U.S. Alt" src="https://user-images.githubusercontent.com/101152/65379218-e7131900-dcc4-11e9-9364-5ee67909229a.png">  | <img alt="English BB Alt" src="https://user-images.githubusercontent.com/101152/65379183-55a3a700-dcc4-11e9-971a-a14f03f66243.png"> |
| ⇧ | <img alt="U.S. Shift" src="https://user-images.githubusercontent.com/101152/65379217-e7131900-dcc4-11e9-9317-a818ba30d949.png"> | <img alt="English BB Shift" src="https://user-images.githubusercontent.com/101152/65379182-55a3a700-dcc4-11e9-87ec-30c6737e01cd.png"> |

## 'English BB 2' based on 'British – PC'

I'm trying to fix the `Cmd+\` issue by basing my layout on British – PC rather than U.S. as the British layout has already the `\` key in the "right" place.

Details:

- Changes a couple of "Shift" keys to be the same as in the U.S. layout:
    - Swaps `@` and `"`
    - Restores `#` to `Shift+3`

## 'Czech BB' customizations

The general idea is to bring it closer to English U.S., incl. the two keys left to the backspace that are often used for zooming etc. This creates a "problem" for Czech accents, e.g., `mód` is now written as `m Alt-<key next to backspace> o d`.

Details:

- Moves <code>&#96;</code> to the top left corner. The overwritten `<` is near the right Shift (with Shift).
- Puts `/` to bottom right corner where `-` normally is. Many apps use `Cmd-/`.
- Moves `-` and `=` to their EN locations. This makes zooming in Chrome etc. work.
    - The new location of `=` overwrites a "dead key comma", e.g. for writing `mód`. This now works with an Alt key (`Alt-=`).
    - Accent for `ť` is at its original Czech location, i.e., `Shift-<key next to backspace>`, but it also works with Alt.
- Also moves `Alt--` (n-dash) so that it's at the same location as on the U.S. keyboard. This rewrites `°` dead key for which there's no new location (`ů` is still available at its normal location which is good enough).

| | Czech QWERTY | Czech BB |
| -- | -- | -- |
|  | <img alt="Czech QWERTY basic" src="https://user-images.githubusercontent.com/101152/65379038-02c8f000-dcc2-11e9-8e2c-585e5399f14e.png"> | <img alt="Czech BB basic" src="https://user-images.githubusercontent.com/101152/65379129-761f3180-dcc3-11e9-93f3-8ab658da79a1.png">
| ⌥ | <img alt="Czech QWERTY Alt" src="https://user-images.githubusercontent.com/101152/65379040-03618680-dcc2-11e9-8a14-68393f5b6a26.png"> | <img alt="Czech BB Alt" src="https://user-images.githubusercontent.com/101152/65379102-23457a00-dcc3-11e9-853c-52e95893b47b.png"> |
| ⇧ | <img alt="Czech QWERTY Shift" src="https://user-images.githubusercontent.com/101152/65379039-02c8f000-dcc2-11e9-80ce-6d38026bbe4f.png"> | <img alt="Czech BB Shift" src="https://user-images.githubusercontent.com/101152/65379101-23457a00-dcc3-11e9-981f-76a7259eddf5.png"> |

### Chrome zooming with the Czech keyboard

According to Chrome's menu and documentation, it zooms via `Cmd-+`. However, that's not entirely true – on an U.S. keyboard, the key between backspace and `-` is not `+` but `=` so actually, `Cmd-=` is being pressed. Chrome somehow makes this work but it's undocumented (at least I couldn't find anything) and it doesn't work for the Czech BB layout even if the key next to backspace is the same `=` as on the U.S. layout.

(Maybe if I also re-mapped `+` to be above `=` as on US keyboard, that would work but I didn't try that.)

A way to fix this is to create a custom shortcut via system Keyboard preferences:

<img width="780" alt="Custom keyboard shortcut for Chrome" src="https://user-images.githubusercontent.com/101152/54015727-dbc12b80-4180-11e9-8a52-10ca9f7d382e.png">

### Czech keyboard when Cmd is pressed

_(Under investigation.)_

U.S. keyboard is the same whether I have or haven't Cmd pressed:

![screenshot 2019-02-27 at 11 42 33](https://user-images.githubusercontent.com/101152/53485013-72a52e00-3a85-11e9-8713-3ea7f9bcc909.png)

However, Czech keyboard changes:

<img width="387" alt="screenshot 2019-02-27 at 11 53 06" src="https://user-images.githubusercontent.com/101152/53485345-45a54b00-3a86-11e9-8831-732f95f79ab9.png">

vs.

<img width="387" alt="screenshot 2019-02-27 at 11 53 50" src="https://user-images.githubusercontent.com/101152/53485380-5d7ccf00-3a86-11e9-924f-6ec72bf01971.png">

The goal is to modify Czech BB so that when Cmd is pressed, it looks exactly like U.S. It could solve a couple of issues with Chrome zoom, GDocs shortcuts and similar.

## Changelog

### 17 Jul 2018

Initial work on "U.S. - PC".

- Move <code>&#96;</code> (backtick) to the top left corner.
    - The overwritten `§` symbol can be written with Alt.
- Move `\` and `|` to the key next to the left Shift (where backtick originally was).
    - The keys are still at their original location next to Enter.

### 22 Feb 2019

Added "Czech - BB" layout.

- Move <code>&#96;</code> to the top left corner. The overwritten `<` is near the right Shift.
- Put `/` to bottom right corner where `-` normally is. Many apps use `Cmd-/`.
- Move `-` and `=` to their EN locations. This makes e.g. zooming in Chrome work.
- Move the dead key comma (e.g. for writing `mód`) to Alt+= (next to backspace)
    - The new location of `=` overwrites a "dead key comma", e.g. for writing `mód`. This now works with an `Alt` key (`Alt-=`).
    - Accent for `ť` is at its original Czech location, i.e., Shift+<key next to backspace>, but it also works with `Alt`.
- Also move `Alt--` (n-dash) so that it's on the same key. This rewrites `°` dead key for which I didn't bother to find a new location yet (`ů` is still on its normal location).

### 16 Sep 2019

Started looking for a solution to the issue with `Cmd-\` – it doesn't work for me in VSCode and Chrome when the backslash is the remapped one (the one next to left shift; it works with the original one). See [Ukelele support thread](https://groups.google.com/forum/#!topic/ukelele-users/28lJPjzbpTQ).

## Other topics

Various notes gathered as I was working on the layouts.

### Resources

- [Awesome overview of Mac keyboard layouts](https://keyshorts.com/blogs/blog/37615873-how-to-identify-macbook-keyboard-localization)
    - [A similar one from Apple](https://support.apple.com/en-us/HT201794)

### Dead keys

Each dead key has a "state" (which is just its name) and a terminator – a character that is either added to an applicable character (like `á`) or written before, like `'1` (numbers can't have accents). The terminator is also committed to the text when a Spacebar is pressed after it.

For Czech BB keyboard, which is a copy of Czech QWERTY, the dead keys are there but they need to be re-mapped. The following cheat sheet is useful for that (the state name / number is visible after double-clicking the key, for example, for `´`, Ukelele tells _Currently, it goes to state "1", which has terminator "'"_):

![screenshot 2019-02-27 at 12 31 51](https://user-images.githubusercontent.com/101152/53487362-aedb8d00-3a8b-11e9-8632-b205a4f723fa.png)

- 1: `´` ([acute](https://en.wikipedia.org/wiki/Acute_accent)) – next to backspace
- 2: `¨` ([umlaut](https://en.wikipedia.org/wiki/Diaeresis_(diacritic))) – next to enter
- 3: `ˇ` ([caron](https://en.wikipedia.org/wiki/Caron)) – `Shift+'`
- 4: `^` ([circumflex](https://en.wikipedia.org/wiki/Circumflex)) – `Alt+'`
- 5: `˚` ([overing](https://en.wikipedia.org/wiki/Ring_(diacritic))) – `Alt+-` (two keys next to backspace)

There are also some other ones with Alt+Shift but I never used them.

Now, for example, to move an acute to `Alt+<key next to backspace>`, it's important to honor the original state / name. So for example, in Ukelele:

1. Press the modified (Alt) and double click the key
2. On the Change State tab, enter 1.
3. Click OK. The key should automatically update to acute (remember that the dead key definition already exists, we're only assigning it to a specific key and a modifier) and when you open the dialog again, it should say _Currently, it goes to state "1", which has terminator "'"_.

### U.S. vs British - PC

| | U.S. | British - PC |
| -- | -- | -- |
| | <img alt="U.S. basic" src="https://user-images.githubusercontent.com/101152/65379219-e7abaf80-dcc4-11e9-9d70-25d8fbc198b0.png"> | <img alt="British - PC basic" src="https://user-images.githubusercontent.com/101152/65379668-f3e73b00-dccb-11e9-99c3-e7cb87019c6c.png"> |
| ⌥ | <img alt="U.S. Alt" src="https://user-images.githubusercontent.com/101152/65379218-e7131900-dcc4-11e9-9364-5ee67909229a.png">  | <img alt="British - PC Alt" src="https://user-images.githubusercontent.com/101152/65379667-f3e73b00-dccb-11e9-83ae-afede6a0edde.png"> |
| ⇧ | <img alt="U.S. Shift" src="https://user-images.githubusercontent.com/101152/65379217-e7131900-dcc4-11e9-9317-a818ba30d949.png"> | <img alt="British - PC Shift" src="https://user-images.githubusercontent.com/101152/65379666-f3e73b00-dccb-11e9-81be-f957f167f116.png"> |

# My macOS keyboard layouts

This repo contains two keyboard layouts, "Czech BB" and "English BB", created with [Ukelele](https://scripts.sil.org/ukelele).

## How to install

1. Copy the keyboard layouts to `/Library/Keyboard Layouts` (not `~/Library/Keyboard Layouts` since that would not allow them on the login screen and in password dialogs):

    ```
    sudo cp -r Czech\ BB.bundle /Library/Keyboard\ Layouts
    sudo cp -r English\ BB.bundle  /Library/Keyboard\ Layouts
    ```

2. Add as Input Sources.

## 'English BB' customizations

- Moves <code>&#96;</code> (backtick) to the top left corner. The overwritten `§` symbol can be written with Alt.
- Moves `\` and `|` to the key next to the left Shift (where backtick originally was).
    - `\` and `|` are still at their original location next to Enter.
    - ❗️ `Cmd-\` shortcut doesn't work in [in VSCode](https://github.com/microsoft/vscode/issues/80697) or in Google Sheets, see this [Ukelele support thread](https://groups.google.com/forum/#!topic/ukelele-users/28lJPjzbpTQ) and [its conclusion](https://groups.google.com/d/msg/ukelele-users/28lJPjzbpTQ/w9sS_UolAgAJ). It only works with the original key (next to Enter).

| | U.S. | English BB |
| -- | -- | -- |
| | <img alt="U.S. basic" src="https://user-images.githubusercontent.com/101152/65379219-e7abaf80-dcc4-11e9-9d70-25d8fbc198b0.png"> | <img alt="English BB basic" src="https://user-images.githubusercontent.com/101152/65379184-563c3d80-dcc4-11e9-81f9-386aae2774ce.png"> |
| ⌥ | <img alt="U.S. Alt" src="https://user-images.githubusercontent.com/101152/65379218-e7131900-dcc4-11e9-9364-5ee67909229a.png">  | <img alt="English BB Alt" src="https://user-images.githubusercontent.com/101152/65379183-55a3a700-dcc4-11e9-971a-a14f03f66243.png"> |
| ⇧ | <img alt="U.S. Shift" src="https://user-images.githubusercontent.com/101152/65379217-e7131900-dcc4-11e9-9317-a818ba30d949.png"> | <img alt="English BB Shift" src="https://user-images.githubusercontent.com/101152/65379182-55a3a700-dcc4-11e9-87ec-30c6737e01cd.png"> |

> **Note**: this layout could also be built from 'British – PC', and you can find an attempt called 'English BB 2' in the repo history. The only change that needed to be done is to fix some Shift combinations: swap `@` and `"` and restore `#` to `Shift+3`.

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

## How to make customizations

Get [Ukelele](https://scripts.sil.org/ukelele): `brew cask install ukelele`. Then:

1. Open an existing bundle or create a new one via **File** > **New From Current Input Source**.
2. Double-click the keyboard layout.
3. On the virtual keyboard, double-click a key you want to remap and enter a character.
4. Give it a name via **Set Keyboard Name and Script...** (this is a different thing than a filename!)
5. [Install](#how-to-install) the keyboard and test it.
6. Update this README – screenshots and [changelog](#changelog).

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

### 22 Sep 2019

- Create a Git repo, deprecate the original Google Drive folder.
- Try to make the `Cmd-\` keyboard shortcut work.
    - It's not possible, a note with explanation has been added [above](#english-bb-customizations).
- Cleanup and rename the keyboards to 'Czech BB' and 'English BB'.
- Heavily update README.

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

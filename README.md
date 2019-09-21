# Keyboards

❤️ [Awesome overview of Mac keyboard layouts](https://keyshorts.com/blogs/blog/37615873-how-to-identify-macbook-keyboard-localization) (and a [similar one](https://support.apple.com/en-us/HT201794) from Apple).

## English U.S. customizations

- Move <code>&#96;</code> (backtick) to the top left corner.
    - Strangely, on "(US) English International Layout" keyboards (with a two-row Enter key), backtick is next to the left Shift.
    - The overwritten `§` symbol can be written with Alt.
- Move `\` and `|` to the key next to the left Shift (where backtick originally was). Czech QWERTY already does that and I find it very natural, especially since `/` is next to the right Shift.
    - `\` and `|` are still at their original location next to Enter.

## Czech (QWERTY) customizations

TL;DR: make it basically the same as English U.S. Solve the accent on the keys next to backspace with Alt, e.g., `mód` is written as `m Alt+<key next to backspace> space o d`.

Details:

- Move <code>&#96;</code> to the top left corner. The overwritten `<` is near the right Shift.
- Put `/` to bottom right corner where `-` normally is. Many apps use `Cmd-/`.
- Move `-` and `=` to their EN locations. This makes e.g. zooming in Chrome work.
- Move the dead key comma (e.g. for writing `mód`) to Alt+= (next to backspace)
    - The new location of `=` overwrites a "dead key comma", e.g. for writing `mód`. This now works with an `Alt` key (`Alt-=`).
    - Accent for `ť` is at its original Czech location, i.e., Shift+<key next to backspace>, but it also works with `Alt`.
- Also move `Alt--` (n-dash) so that it's on the same key. This rewrites `°` dead key for which I didn't bother to find a new location yet (`ů` is still on its normal location).

### Chrome zooming

According to its menu, documentation and many resources on the web, Chrome zooms in via `Cmd-+`. However, that's not entirely true – on an US keyboard, the key between backspace and `-` is not `+` but `=` so actually, one presses `Cmd-=`. Chrome makes this work, somehow, but it's undocumented (at least I couldn't find anything) and it doesn't work for my "Czech BB" layout even if the key next to backspace is the same `=` as on US layout.

(Maybe if I also re-mapped `+` to be above `=` as on US keyboard, that would work but I didn't try that.)

A way to fix this is to create a custom shortcut via system Keyboard preferences:

<img width="780" alt="screenshot 2019-03-08 at 09 01 50" src="https://user-images.githubusercontent.com/101152/54015727-dbc12b80-4180-11e9-8a52-10ca9f7d382e.png">

This makes "Cmd and the keyboard next to backspace" work.

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

### Keyboard when Cmd is pressed

(Under investigation.)

U.S. keyboard is the same whether I have or haven't Cmd pressed:

![screenshot 2019-02-27 at 11 42 33](https://user-images.githubusercontent.com/101152/53485013-72a52e00-3a85-11e9-8713-3ea7f9bcc909.png)

However, Czech keyboard changes:

<img width="387" alt="screenshot 2019-02-27 at 11 53 06" src="https://user-images.githubusercontent.com/101152/53485345-45a54b00-3a86-11e9-8831-732f95f79ab9.png">

vs.

<img width="387" alt="screenshot 2019-02-27 at 11 53 50" src="https://user-images.githubusercontent.com/101152/53485380-5d7ccf00-3a86-11e9-924f-6ec72bf01971.png">

The goal is to modify Czech BB so that when Cmd is pressed, it looks exactly like U.S. It could solve a couple of issues with Chrome zoom, GDocs shortcuts and similar.

## How to make customizations

It's done via [Ukelele](https://scripts.sil.org/ukelele) (`brew cask install ukelele`).

1. Open an existing bundle or create a new one via **File** > **New From Current Input Source**.
2. Double-click the keyboard layout.
3. On the virtual keyboard, double-click a key you want to remap and enter a character.
4. Give it a name via **Set Keyboard Name and Script...** (this is a different thing than a filename!)
5. Install:
    ```
    sudo cp -r ~/Drive/AppSettings/Mac/Xyz.bundle /Library/Keyboard\ Layouts
    ```
    - There's also a built-in "Organiser" in Ukelele (**File** > **Install** > **Show Organizer**) but that [removes the bundle from Google Drive](https://groups.google.com/forum/#!topic/ukelele-users/90YkwlJoCIg).
6. Log out & log in.
    - It's also possible to remove the keyboard layout from Input Sources and add it back in.
7. Select keyboard in Input Sources.

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

As a result, I might be trying [Karabiner-Elements](https://pqrs.org/osx/karabiner/).

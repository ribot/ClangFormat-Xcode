# ClangFormat-Xcode (with [ribot](http://ribot.co.uk) additions)

An Xcode plug-in to format your code using Clang's format tools, by [@travisjeffery](https://twitter.com/travisjeffery).

With [clang-format](http://clang.llvm.org/docs/ClangFormat.html) you can use Clang to format your code to styles such as LLVM, Google, Chromium, Mozilla, WebKit, or your own configuration.

## Installation:

1. Clone this repo: `git clone https://github.com/ribot/ClangFormat-Xcode.git --depth 1`
2. Open `ClangFormat.xcodeproj`: `open ClangFormat-Xcode/ClangFormat.xcodeproj`
3. Run the project
4. Restart XCode
5. Turn on formatting by file: _*Edit* menu -> *Clang Format* -> Tick *File*_

## Usage:

![usage](https://raw.github.com/travisjeffery/ClangFormat-Xcode/master/README/usage.png)

![demo](https://raw.github.com/travisjeffery/ClangFormat-Xcode/master/README/clangformat-xcode-demo.gif)

### Format on save

I.e., you press `command-s` and the file is formatted and wrote to disk.

In the menu, open Edit > Clang Format > Click Format on save (a checkmark appears in this menu item indicicating that the feature is active.)

### Assign keyboard shortcuts

You can assign your own keyboard shortcuts like so:

- Open the System Preferences > Keyboard > Shortcuts > App Shortcuts > Click +
- Set the application to be Xcode
- Set the menu title to an action title, e.g. "Format File in Focus"
- Set your shortcut

In this example, we'll format the active file when `control-i` is pressed.

![assign keyboard shortcut](https://raw.github.com/travisjeffery/ClangFormat-Xcode/master/README/assign-keyboard-shortcut.png)

### Using your own style configuration

By using Clang Format > File in the plug-in menu, Clang will look for the nearest `.clang-format` file from the input file. Most likely, you'll have a .clang-format file at the root of your project.

[Here are the options for .clang-format and how they're configured](http://clang.llvm.org/docs/ClangFormatStyleOptions.html).

If one of the built-in styles is close to what you want, you can bootstrap your own configuration with:

`./bin/clang-format -style=llvm -dump-config > .clang-format`

For example, this .clang-format is similar to the [Linux Kernel style](https://www.kernel.org/doc/Documentation/CodingStyle):

```
BasedOnStyle: LLVM
IndentWidth: 8
UseTab: Always
BreakBeforeBraces: Linux
AllowShortIfStatementsOnASingleLine: false
IndentCaseLabels: false
```

And this is similar to Visual Studio's style:

```
UseTab: Never
IndentWidth: 4
BreakBeforeBraces: Allman
AllowShortIfStatementsOnASingleLine: false
IndentCaseLabels: false
ColumnLimit: 0
```

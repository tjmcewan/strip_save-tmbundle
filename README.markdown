TextMate Macro to strip trailing spaces from line ends (but not indentation placeholders) then save.

**NB: This macro is assigned the Command+S shortcut by default; it overrides the *normal* save shortcut.**

It runs this:
    #!/usr/bin/env ruby

    doc_text = STDIN.read
    puts doc_text.gsub(/\b[\t ]+$/, '')
and then saves using the built-in save command.

To INSTALL paste this into Terminal:

`git clone git://github.com/tmcewan/strip_save-tmbundle.git ~/Library/Application\ Support/TextMate/Bundles/strip_save.tmbundle; osascript -e 'tell app "TextMate" to reload bundles'`

NOT HAPPY?

You can edit the Macro file directly using TextMate:

`mate ~/Library/Application\ Support/TextMate/Bundles/strip_save.tmbundle/Macros/strip\ \&\ save.tmMacro`

Make the `puts` line read this: `puts doc_text.gsub(/[\t ]+$/, '')` to strip *all* trailing spaces/tabs - even the ones that would keep your cursor correctly indented.

Note: using `puts` always adds a new line at EOF (if there isn't one already) to stop this behaviour use `print`

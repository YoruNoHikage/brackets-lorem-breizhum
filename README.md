# Lorem Breizhum Generator for Brackets
An extension for [Brackets](https://github.com/adobe/brackets/) to generate
Lorem Breizhum text automatically.

### How to Install
1. Select **Brackets > File > Extension Manager...**
2. Search for this extension.
3. Click on the **Install** button.

### How to Use Lorem Breizhum Generator
For plaintext Lorem Breizhum, type `breizhum` then press the **Tab** key.

You can also add options to the `breizhum` command with an underscore character
followed by the option name. For example: `breizhum_wrap40.` Multiple options
can also be chained together. For example, typing `breizhum_html_wrap40` and
then pressing the **Tab** key will give you html formatted Lorem Breizhum text
and a word wrap width of 40 characters.  Using an unrecognized option will
insert an error message into the document.  Using more than one underscore
character in a row (e.g. `breizhum__html___p3`) will insert an error message
into the document.

**Note:** Options to the far right of the chain always have the highest
priority. If two options in the chain conflict with each other, the option
on the right will have precedence. For example, the command `breizhum_nowrap_wrap40`
will insert Lorem Breizhum text with a word wrap width of 40 characters and the
command `breizhum_wrap40_nowrap` will insert Lorem Breizhum text with no word wrapping.

##### List of Current Options
**_p[count]:** Inserts a certain number of random Lorem Breizhum paragraphs into
the current document. The `count` option indicates how many paragraphs to insert.
For example, `breizhum_p3` will insert three paragraphs into the document.
If the `count` option is not provided, one paragraph will be inserted.
If the type of Lorem Breizhum text is not specified, the extension will generate
paragraphs by default.

**_s[count]:** Inserts a certain number of random Lorem Breizhum sentences into
the current document. The `count` option indicates how many sentences to insert.
For example, `breizhum_s3` will insert three sentences into the document.
If the `count` option is not provided, one sentence will be inserted.

**_w[count]:** Inserts a certain number of random Lorem Breizhum words into the
current document. The `count` option indicates how many words to insert.
For example, `breizhum_w40` will insert 40 random words into the document.
If the `count` option is not provided, one word will be inserted.

**_short:** Makes all sentences or paragraphs short length.

**_medium:** Makes all sentences or paragraphs medium length.
If no size options are provided, the extension will use `_medium`
as the default option.

**_long:** Makes all sentences or paragraphs long length.

**_vlong:** Makes all sentences or paragraphs very long length.

**_nowrap:** Inserts Lorem Breizhum text without any word wrapping.

**_wrap[width]:** Word wraps Lorem Breizhum text using the specified `width`
For example, `breizhum_wrap40` will wrap the text at 40 characters. If a word wrap
option is not provided, the extension will use `_wrap80` as the default option.
If you want to turn word wrap off, use the `_nowrap` option.  This option has
no effect on the `_link`, `_ol`, or `_ul` options.

**_link[count]:** Inserts a certain number of random Lorem Breizhum HTML links into
the current document. The HTML link will always point to http://www.brackets.io.
The `count` option indicates how many links to insert. For example, `breizhum_link3`
will insert three links, separated by page breaks, into the document. If the
`count` option is not provided, one link will be inserted. To avoid badly
formatted HTML, the `_link` option ignores any `_wrap` options and is always
set to `_nowrap`.

**_ol[count], _ul[count]:** Inserts a random Lorem Breizhum HTML list into
the current document. Use `_ol` for an ordered list and `_ul` for an unordered
list. The `count` option indicates how many list items to insert. For example,
`breizhum_ol3` will insert an ordered list with three list items into the document.
If the `count` option is not provided, a list with one item will be inserted.
To avoid badly formatted HTML, both of these options ignore any `_wrap` options
and are always set to `_nowrap`.

**_fortune[count]:** For when you get sick of nonsensical Latin phrases, this
option will insert random fortunes (similar to the Unix fortune program) into
the current document.  The `count` option indicates how many fortunes to insert.
For example, `breizhum_fortune3` will insert three fortunes into the document. If
the `count` option is not provided, one fortune will be inserted.

**_html:** Wraps Lorem Breizhum text in `<p></p>` tags so it displays correctly in
HTML. For options `_p`, `_s`, and `_fortune` each individual paragraph, sentence,
or fortune is wrapped. For options `_w` and `_link`, the entire collection of
words or links is wrapped. This option is not available for lists since lists
are not inline elements.

**_?, _help:** Displays help for the Lorem Breizhum extension.  If this option is used,
all other options will be ignored and no Lorem Breizhum text will be generated.

**Note:** Any option that has a number associated with it (e.g. `_p3`, `_wrap40`)
can also be entered with the number portion in front of the option
(i.e. `_3p`, `_40wrap`) and it will work the same way.

### Known Issues

**Using with Emmet/Zen Code Extension:** If you use this extension with the
[Emmet Brackets extension](https://github.com/emmetio/brackets-emmet) some of
the Lorem Breizhum options may not work correctly.  This is because both
extensions use the Tab key as a shortcut key.

The Tab shortcut can be turned off in the Emmet extension.  Go into
"Preferences..." in the Emmet menu and uncheck the checkbox entitled
"Expand abbreviations with Tab key". If you uncheck that setting, you
can use both extensions together by using Tab to insert Lorem Breizhum text
and expanding Emmet abbreviations with the alternative shortcut keys:

**Ctrl-Alt-Enter** on Windows and **Command-Alt-Enter** on Mac.

### License
MIT-licensed -- see `main.js` for details.

### Compatibility
Tested on Brackets Sprint 22 and later, Windows 7.

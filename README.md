# Spell Check Plus package
[![OS X Build Status](https://travis-ci.org/gucciferXCIV/spell-check-plus.svg?branch=master)](https://travis-ci.org/gucciferXCIV/spell-check-plus) [![Dependency Status](https://david-dm.org/gucciferxciv/spell-check-plus.svg)](https://david-dm.org/gucciferxciv/spell-check-plus)

Highlights misspellings in Atom and shows possible corrections.

Installation:
----------

1. Disable the core *Spell Check* atom package. To disable it:

* Open atom's Settings View. This can be done any of the following ways:
  * By going to *File > Settings* in the menu bar
  * By using the <kbd>Ctrl+,</kbd> / <kbd>Cmd+,</kbd> keybinding
  * By searching for `settings-view:open` in the [Command Palette](http://flight-manual.atom.io/getting-started/sections/atom-basics/#command-palette) (<kbd>Ctrl+Shift+P</kbd> / <kbd>Cmd+Shift+P</kbd>)
* Click the Packages tab in the sidebar
* Search for the *spell-check* package
* Click "Disable" for the *spell-check* package

2. Open your terminal, e.g. bash, cmd, terminal
3. Enter `apm install gucciferxciv/spell-check-plus`

...and that's it.

To configure the `Disabled Scopes`, open *Spell Check Plus*'s settings, and add the scopes you want ignored to `Disabled Scopes` as a list of values, each separated by a comma and a space.

Detailed instructions for enabling and disabling scopes, and other config options are included below.

----------

You can pull up a menu of possible corrections by hitting <kbd>Ctrl+:</kbd> / <kbd>Cmd+:</kbd>, or by choosing "Correct Spelling" from the right-click context menu or from the Command Palette.

By default *Spell Check Plus* is enabled for the following files:

* Plain Text as `text.plain` and `text.plain.null-grammar`
* GitHub Markdown as `source.gfm`
* Git Commit Message as `text.git-commit`
* AsciiDoc as `source.asciidoc`

You can override this from the *Spell Check Plus* settings in the Settings View. The Scopes config option is a list of scopes for which the package will check for spelling errors, and the Disabled Scopes config option is a list of scopes for which the package will skip checking for spelling errors in files for which the main scope has been enabled.

To enable *Spell Check Plus* for your current file type, you have to add it's main Scope string. The easiest way to determine what this should be is to go to the language package of the language you want to add and look for the "Scope" string. You can also put your cursor in the file, open the Command Palette, and run the `Editor: Log Cursor Scope` command. This will trigger a notification which will contain a list of scopes. The first scope that's listed is the one you should add to the list of scopes in the settings for the *Spell Check Plus* package. Here are some examples: `source.coffee`, `text.plain`, `text.html.basic`.

To disable *Spell Check Plus* for all instances of a specific scope within a file's main scope for which the *Spell Check Plus* package is enabled, put your cursor in any instance of the type of section you want ignored. For example, if you have Markdown files enabled, i.e. `source.gfm`, but you don't want any URLs in `[link_text](URL)` type links to to be checked for spelling, you'd put your cursor anywhere within the URL part, open the Command Palette, and run `Editor: Log Cursor Scope`. In this example, the first scope is the main scope for the file, the second is the scope for the whole link from `[` to `)`, and the third is the scope for the URL within the link, which is the one you'd want to add to Disabled Scopes. Be aware that `Editor: Log Cursor Scope` does __not__ always return three scopes, however, the scopes *are* always returned in order of specificity, making it fairly easy to figure out which scope is the one you need.

*Note:* Disabled Scopes should not be used to ignore whole files. Instead, just make sure the scope for the file type you don't want checked isn't in Scopes.

## Changing the dictionary

To change the language of the dictionary, set the "Locales" configuration option to the IETF tag (en-US, fr-FR, etc). More than one language can be used, simply separate them by commas.

For Windows 8 and 10, you must install the language using the regional settings before the language can be chosen inside Atom.

## Plugins

*Spell Check Plus* allows for plugins to provide additional spell checking functionality. See the `PLUGINS.md` file in the repository on how to write a plugin.

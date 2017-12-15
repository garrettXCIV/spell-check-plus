# Spell Check Plus package
[![OS X Build Status](https://travis-ci.org/gucciferxciv/spell-check-plus.svg?branch=master)](https://travis-ci.org/gucciferxciv/spell-check-plus) [![Dependency Status](https://david-dm.org/gucciferxciv/spell-check-plus.svg)](https://david-dm.org/gucciferxciv/spell-check-plus)

Highlights misspelling in Atom and shows possible corrections.

To install spell-check-plus in atom:
----------

1. Disable the core `spell-check` atom package. To disable it:

* Open your settings by going to `File > Settings` or by pressing: <kbd>ctrl</kbd>+<kbd>,</kbd> / <kbd>cmd</kbd>+<kbd>,</kbd>
* Click packages
* Search for `spell-check`
* Click "Disable" for the `spell-check` package

2. Open your terminal, e.g. bash, cmd
3. Enter `apm install gucciferxciv/spell-check-plus`

...and that's it.

To configure your `Disabled Grammars`, when you open Atom:


* Open `Settings` for `spell-check-plus`, in atom's package settings and add the scopes you want ignored under `Disabled Grammars`

Instructions for enabling and disabling grammars, and other config options are included below.

----------

Use <kbd>cmd-shift-:</kbd> to bring up the list of corrections when your cursor is on a misspelled word.

By default spell check plus is enabled for the following files:

* Plain Text
* GitHub Markdown
* Git Commit Message
* AsciiDoc

You can override this from the _Spell Check Plus_ settings in the Settings View (<kbd>cmd-,</kbd>). The Grammars config option is a list of scopes for which the package will check for spelling errors, and the Disabled Grammars config option is a list of scopes for which the package will skip checking for spelling errors in files for which the main scope has been enabled.

To enable _Spell Check Plus_ for your current file type: put your cursor in the file, open the [Command Palette](https://github.com/atom/command-palette)
(<kbd>cmd-shift-p</kbd>), and run the `Editor: Log Cursor Scope` command. This will trigger a notification which will contain a list of scopes. The first scope that's listed is the one you should add to the list of scopes in the settings for the _Spell Check Plus_ package. Here are some examples: `source.coffee`, `text.plain`, `text.html.basic`.

To disable _Spell Check Plus_ for all instances of a specific scope within a file's main scope for which the package is enabled, put your cursor in any instance of the type of section you want ignored. For example, if you have Markdown files enabled, but you don't want any URLs in `[link_text](url)` type links to to be checked for spelling, you'd put your cursor anywhere within the URL part, open the Command Palette (see previous paragraph), and enter `Editor: Log Cursor Scope`. In this example, the first scope is the main scope for the file, the second is the scope for the whole link, and the third is the scope for the URL within the link, which is the one you'd want to add to Disabled Grammars. Be aware that `Editor: Log Cursor Scope` does __not__ always return three scopes, however, the scopes are always returned in order of specificity, making it fairly easy to figure out which scope is the one you need.

*Note:* Disabled Grammars should not be used to ignore whole files. Instead, just make sure the scope for the file type you don't want checked isn't in Grammars.

## Changing the dictionary

To change the language of the dictionary, set the "Locales" configuration option to the IETF tag (en-US, fr-FR, etc). More than one language can be used, simply separate them by commas.

For Windows 8 and 10, you must install the language using the regional settings before the language can be chosen inside Atom.

## Plugins

_Spell Check Plus_ allows for plugins to provide additional spell checking functionality. See the `PLUGINS.md` file in the repository on how to write a plugin.

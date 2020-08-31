## shellnote

Easy note-taking on the command line.

The idea behind `shellnote` is to enable quick note-taking while you're working or reading. If an idea pops into your head, or you need to remember something, just jot down in your terminal:

`shellnote -a "This is a great idea."`

Your entry will be saved with a timestamp in a tab-delimited text file, `~/shellnote.txt`. You can print the last 20 lines using the `-p` flag:

	martin@t480s ~ % shellnote -p	
	2020-08-29  19:57   Richard Stallman really whips the llama's ass.
	2020-08-29  20:12   Make sure to drink your Ovaltine.
	2020-08-29  20:24   This is a great idea.

## Installation

Clone this repo to your local drive and copy/link `shellnote` into a folder in your path and make sure it is executable (`chmod +x shellnote`).

## Basic use and configuration

By default, `shellnote` will populate a text file in your /home directory. If it exists, `shellnote` will load ~/.shellnoterc with your configurations. To see available configuration options, copy the default .shellnoterc in this repo to ~/.shellnoterc and edit it.

Available command line options:

	-a	Add a new  entry
	-e	Edit current entries in external editor
	-d	Delete last entry
	-h	Print this help
	-p	Print the last 20 entries
	-P	Print the last 20 entries with pretty formatting
	-s	Search entries (supports regex)

I recommend making an alias to your liking in your shell config file; e.g., `alias note='shellnote'`. Now you just need to write `note -a "This is an even greater idea!"` to add an entry, or `note -p` to print entries.

## Known bugs

* Entries need to be surrounded with single or double quotes, as otherwise only the first word gets logged.
* You need to espace interpreted characters such as `\t` or shell variables such as `$SHELL`; e.g., `shellnote -a "A tab can be had: \\\t"` or `shellnote -a "My shell is $SHELL, which I can tell with \$SHELL."`.

## About
Written by Martin Gustavsson, released under GPLv3 license. 

This is my first shell script, so please leave suggestions or pull requests for improvements.

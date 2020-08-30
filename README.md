## shellnote

Easy note-taking on the command line.

The idea with `shellnote` is to enable quick note-taking while you're working or reading. If an idea pops into your head, or you need to remember something, just jot down in your terminal:

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

All command line options:

	-a	Add a new  entry
	-e	Edit current entries in external editor
	-d	Delete last entry
	-h	Print this help
	-p	Print the last 20 entries

I recommend making an alias in your shell config file to `shellnote -a` to your liking; e.g., `alias note='shellnote -a'`. Now you just need to write

 `note "This is an even greater idea!"`.

## Known bugs

* For now it's recommended to surround your entry with single or double quotes, as otherwise only the first word gets logged, or certain characters are not escaped properly.

## About
Written by Martin Gustavsson, released under GPLv3 license. 

This is my first shell script, so please leave suggestions or pull requests for improvements.

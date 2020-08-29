## shellnote

Easy note-taking on the command line.

By default, `shellnote` will populate a text file in your /home directory. If it exists, shellnote will load ~/.shellnoterc with your configurations. To see available configuration options, copy the default .shellnoterc in this repo to ~/.shellnoterc and edit it.

## Installation

Clone this repo to your local drive and move `shellnote` into a folder in your path and make sure it is executable (`chmod +x shellnote`).

## Basic usage

The idea with `shellnote` is to enable quick note-taking while you're working or reading. If an idea pops into your head, or you need to remember something, just jot down in your terminal:

`shellnote -a "This is a great idea."`

Other options are:

 -a		Add an entry

 -d		Delete last entry

 -h		Print this help

 -p		Print the current log file

I recommend making an alias in your shell config file to `shellnote -a` to your liking; e.g., `alias note='shellnote -a'`. Now you just need to write `note "This is an even greater idea!"`.

## Known bugs

* For now it's recommended to surround your entry with single or double quotes, as otherwise only the first word gets logged, or certain characters are not escaped properly.

## About
Written by Martin Gustavsson, released under GPLv3 license. 

This is my first shell script, so please leave suggestions or pull requests for improvements.

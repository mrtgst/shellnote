	         __         ____            __
	   _____/ /_  ___  / / /___  ____  / /____
	  / ___/ __ \/ _ \/ / / __ \/ __ \/ __/ _ \
	 (__  ) / / /  __/ / / / / / /_/ / /_/  __/
	/____/_/ /_/\___/_/_/_/ /_/\____/\__/\___/
	 - easy note-taking on the command line.

The idea behind `shellnote` is to enable quick note-taking while you're working or reading. If an idea pops into your head, or you need to remember something, just jot down in your terminal:

`shellnote -a "This is a great idea."`

There is also a short-hand available:

`note -a "This is an even greater idea!"`

Your entry will be saved with a timestamp in a tab-delimited text file, `~/shellnote.txt`. You can print the entry log using the `-p` flag:

	martin@t480s ~ % note -p
	2020-08-29  19:57	Richard Stallman really whips the llama's ass.
	2020-08-29  20:12	Make sure to drink your Ovaltine.
	2020-08-29  20:24	This is a great idea.
	2020-08-29  20:25	This is an even greater idea!

`shellnote` is POSIX compliant and should work in most Unix shells.

## Installation

To install `shellnote`, clone this repo using 
`git clone https://github.com/mrtgst/shellnote.git`
and follow the instructions below.

### Using the install script
Run the `install` script by navigating to the repo folder and enter `sudo ./install`. This will copy `shellnote` to `/usr/local/bin/` and also create a soft link called `note` in the same folder. This enables running `shellnote` with `note`, without needing to set an alias. If the installation is successful but `shellnote` doesn't run, make sure `/usr/local/bin/` is in your path variable.

### Manually
Copy/link `shellnote` into a folder in your path and make sure it is executable (`chmod +x shellnote`).

To enable the `note` short-hand, either copy the `note` symbolic link in the repo to the same folder you put `shellnote` in, or create an alias in your shell config file: `alias note='shellnote'`.

## Basic use and configuration

By default, `shellnote` will populate a text file in your /home directory. If it exists, `shellnote` will load ~/.shellnoterc with your configurations. To change configuration, copy the default .shellnoterc in this repo to ~/.shellnoterc and edit it.

Available command line options:

	-a	Add a new entry
	-e	Edit current entries in your text editor
	-d	Delete last entry
	-h	Print this help
	-p	Print entries
	-s	Search entries (supports regex)

## Known limitations 

* Entries need to be surrounded with single or double quotes, as otherwise only the first word gets logged.
* You need to escape interpreted characters such as `\t` or shell variables such as `$SHELL`; e.g., `shellnote -a "A tab can be had: \\\t"` or `shellnote -a "My shell is $SHELL, which I can tell with \$SHELL."`.

## About
Written by Martin Gustavsson, released under GPLv3 license. 

This is my first shell script, so please leave suggestions or pull requests for improvements.

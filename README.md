	         __         ____            __
	   _____/ /_  ___  / / /___  ____  / /____
	  / ___/ __ \/ _ \/ / / __ \/ __ \/ __/ _ \
	 (__  ) / / /  __/ / / / / / /_/ / /_/  __/
	/____/_/ /_/\___/_/_/_/ /_/\____/\__/\___/
	 $ easy note-taking on the command line.

The idea behind `shellnote` is to enable quick note-taking while you're working or reading. If an idea pops into your head, or you need to remember something, just jot down in your terminal:

`shellnote -a "This is a great idea."`

Your entry will be saved with a timestamp in a tab-delimited text file. You can print the entry log using the `-p` flag:

	martin@t480s ~ $ shellnote -p
	2020-08-29  19:57	Richard Stallman really whips the llama's ass.
	2020-08-29  20:12	Make sure to drink your Ovaltine.
	2020-08-29  20:24	This is a great idea.

`shellnote` is POSIX compliant and should work in most Unix shells.

## Installation

To install, download this repo and run the install script: 

```
git clone https://github.com/mrtgst/shellnote.git
cd shellnote
sudo ./setup install
``` 

This will copy `shellnote` to `/usr/local/bin/`.

To create a handy `note` shorthand you can create an alias in your shell's config or aliases file; e.g., if you use bash:

```
echo "alias note='shellnote'" >> "$HOME"/.bashrc
```

## Uninstallation

To remove shellnote and its config file you can call the above setup-script with `sudo ./setup uninstall`. This will not delete your notes.

## Basic use

By default, `shellnote` will populate a text file `shellnote.txt` in your home directory. 

Available command line options:

	-a	Add a new entry
	-e	Edit current entries in your text editor
	-d	Delete last entry
	-h	Print this help
	-p	Print entries
	-s	Search entries (supports regex)
	-v	Print verbose messages

## Configuration

The install script creates a config file `/etc/shellnote/shellnote.conf` with the default configuration. 

You can create a user config file in `~/.config/shellnote/shellnote.conf`. The settings in this file will override any other.

## Known limitations 

* Entries need to be surrounded with single or double quotes, as otherwise only the first word gets logged.
* You need to escape interpreted characters such as `\t` or shell variables such as `$SHELL`; e.g., `shellnote -a "A tab can be had: \\\t"` or `shellnote -a "My shell is $SHELL, which I can tell with \$SHELL."`.

## About
Written by Martin Gustavsson, released under GPLv3 license. 

# vtsay

## Summary

This program converts text to audible speech via the Voice Text Web
API. The speech is played back using `play`, `aplay` or `paplay`
command, from `sox`, `alsa-utils` and `pulseaudio-utils` packages
respectively.

## Dependencies

* `curl` command.
* One of the player commands mentioned above.
* Ruby :)

## Installation

First, acquire your API key on the Voice Text web site
https://cloud.voicetext.jp/webapi .  They will send you the key via
email. Save the key in the file `~/.voiceapi`.

`$ ruby vtsay` should print help information at this point.

If `$ ./vtsay` does not also work, you may need to change the shebang
line at the top of the vtsay source file to point to where the ruby
interpreter is installed on your system.

Copy the file to some directory that is in the $PATH, like so:

	sudo install -m 0755 vtsay /usr/local/bin

## Usage

```
Usage: vtsay [-v voice] [-o out.wav] [-f file.in | string ...]

-v [show|haruka|hikari|takeru|santa|bear]
-o outfile
-f infile

--speaker=[show|haruka|hikari|takeru|santa|bear]
--format=[ogg|wav|mp3] (defaults to ogg)
--emotion=[happiness|anger|sadness] (only for haruka, hikari, takeru, santa, or bear)
--emotion-level=NUMBER (range 1-4, also --emotion_level)
--pitch=NUMBER (percentage, range 50-200)
--speed=NUMBER (percentage, range 50-400)
--volume=NUMBER (percentage, range 50-200)

--debug
        print debug messages
--version
        print version information and exit
--help
        display this help and exit
```

## Examples

Read aloud:

	vtsay おはようございます

Save as a WAV file:

    vtsay -o output.wav こんにちは

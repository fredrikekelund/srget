# SR Get
> [Sveriges Radio](sverigesradio.se) (SR) local cache tool

You can use this script to download all the available audio files from a show's
feed, or to download the audio from an individual episode.

When used to download audio from the feed of a show, a local cache is saved to
keep track of what episodes have been downloaded. That means you can run the
script periodically with the same arguments to get an up-to-date local copy of
all the episodes of an SR show (ie. this script is
[cron](https://en.wikipedia.org/wiki/Cron) friendly).

## Prerequisites
To run the script you need to have PHP (including the `php-json` extension)
installed. On Linux, use your package manager to install the necessary packages,
on OS X PHP should already be installed, and for Windows you can download an
installer [here](http://php.net/downloads.php). This script has only been tested
with PHP 5.6.

## Installation
To use this script, download the `srget` file and give it permission to be
executed as a program. To set those permissions on Linux or OS X, simply run:
```sh
$ chmod +x srget
```

## Usage
The script takes a sverigesradio.se URL as the only argument and automatically
recognizes whether it leads to a show or an episode.

You can download an individual episode like this:
```sh
$ ./srget http://sverigesradio.se/sida/avsnitt/652692?programid=2794
```

And you can download the latest episodes of a show (that haven't already been
downloaded) like this:
```sh
$ ./srget http://sverigesradio.se/sida/avsnitt?programid=516
```

### Moving the audio files
The feed cache is just a small text file (`cache.json`) that's independent from
the audio files that are downloaded. So feel free to move the audio files around
after the download has finished!

## See also
If you want to download from [SVT Play](http://www.svtplay.se/), have a look at
the excellent [svtget](https://github.com/mmn/svtget).

## License
This project is licensed under the [Unlicense](http://unlicense.org/). See the
LICENSE file for more information.
